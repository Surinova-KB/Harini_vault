

Since RPI has no inbuild CAN controller in the system, MCP251863 which is a controller + transceiver is used for CAN transmission.

The communication format:
RPI --> SPI --> MCP251863 --> CAN Bus

RPI sends data to MCP via SPI and MCP pushed the data into CAN bus.


### CAN overlay:

   To make Rpi send data through SPI,UART or any communication protocol , it needs to be enabled and overlayed in the firmware.

   Before overlaying connect the MCP module to RPi via SPI only then the overlay is valid.
   
   command to open the config file:
   
    sudo nano /boot/firmware/config.txt     

     dtparam=spi=on

     ls dev/spidev*   
     
   Should return spi0.0 this confirms spi is enabled and available to transmit data.

     dtoverlay=mcp251xfd,spi0-0,interrupt=25,oscillator=40000000
   Command overlays mcp and install necessary drivers for linux to drive mcp.
   at last save and reboot and verify MCP is overlayed properly
     `dmesg | grep spi`  
   This should print something relevant to MCP. Then overlay is done and functioning.


### CAN Configuration:

   In the terminal run these following command make sure mcp is connected to Rpi while this is done:

     suod ip link set can0 down

     sudo ip link set can0 type can bitrate 250000 fd off loopback off sample-point 0.857      prop-seg 5 phase-seg1 6 phase-seg2 2 sjw 1  

      suod ip link set can0 up

  Now CAN is up and running but this only stays active until reboot. On every reboot  these steps need to be repeated to bring CAN up.

  It's solved by setting CAN bring up on boot in Rpi4.

### CAN Bring up on Boot :

  Navigate to `/usr/local/bin`

     cd /usr/local/bin

    touch can-start.sh    
  can-start.sh file is created in /usr/local/bin.

 Paste the configuration commands into can-start.sh

   `#!/bin/bash`
   `/sbin/ip link set can0 down`
   `/sbin/ip link set can0 type can bitrate 250000 prop-seg 5 phase-seg1 6 phase-seg2 2 sjw   1 restart-ms 100`
   `/sbin/ip link set can0 up`

   save and exit 
   Make the file executable
    `sudo chmod +x /usr/local/bin/can-start.sh`

   Then,
     `cd /etc/systemd/system`

     touch can-interface.service

  creates a .service file for CAN
  Paste the below snippet into can-interface.service:

	[Unit]
	Description=Setup CAN0 Interface
	After=network.target
	
	[Service]
	Type=oneshot
	User=root
	Group=root
	ExecStart=/usr/local/bin/can-start.sh
	RemainAfterExit=yes
	
	[Install]
	WantedBy=multi-user.target


	 cd /etc/udev/rules.d
     touch 99-can0.rules

     ACTION=="add", SUBSYSTEM=="net", KERNEL=="can0", RUN+="/usr/local/bin/can-start.sh"

      sudo udevadm control --reload-rules && sudo udevadm trigger

Reboot and check now can must be up and running.
