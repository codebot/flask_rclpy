# greetings

On Ubuntu 20.04:
```
sudo apt install python3-flask python3-dotenv
```

# test pub/sub through Flask
First start publishing stuff onto `/topic` using a sample rclpy program:
```
. /opt/ros/foxy/setup.bash
ros2 run examples_rclpy_minimal_publisher publisher_member_function
```

In another terminal, run the rclpy+Flask demo program:
```
. /opt/ros/foxy/setup.bash
./run.sh
```

In another terminal, query the latest message via flask whenever you want:
```
curl http://localhost:5000/latest_message
```

In another terminal, echo `/flask_pub_topic`:
```
. /opt/ros/foxy/setup.bash
ros2 topic echo /flask_pub_topic
```

In another terminal, ask Flask to publish a ros2 message onto that topic:
```
curl http://localhost:5000/publish_message
```
