# setup

Let's create a virtual environment named `venv` for all this Python magic:
```
sudo apt install python3-venv
python3 -m venv venv
```

Now let's activate the Python virtual environment so we can install all sorts of things into it without breaking our system:
```
. venv/bin/activate
pip install flask python-dotenv
```

Now run the flask+rclpy demo program in the venv, assuming you still have a shell with the venv activated in it:
```
. /opt/ros/foxy/setup.bash
./run.sh
```

In another shell, start publishing stuff onto `/topic` using a sample rclpy program:
```
. /opt/ros/foxy/setup.bash
ros2 run examples_rclpy_minimal_publisher publisher_member_function
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
