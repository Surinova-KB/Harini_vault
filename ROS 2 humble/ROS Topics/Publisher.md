A block of code mostly part of a node which puts data into a ROS topic. 

Syntax:

  Normal publihser:
     limited_velocity_publisher_ = get_node()->create_publisher<TwistStamped>(
      DEFAULT_COMMAND_OUT_TOPIC, rclcpp::SystemDefaultsQoS());

Realtime-publisher warpper:
    realtime_limited_velocity_publisher_ =
    std::make_shared<realtime_tools::RealtimePublisher<TwistStamped>>(
        limited_velocity_publisher_);





The controller publishes _via the realtime publisher_ → which pushes to the underlying normal publisher safely.