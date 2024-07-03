# Troubleshooting
Common issues and troubleshooting steps will be added here.

* **If you get this error message:**
    <img width="1238" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/9c6b8644-3b5a-4e64-981e-5691c2c4ed55">
        
    Follow these steps:
    1. **Clear Previous ROS Environment Variables:**
        ```bash
        unset ROS_DISTRO
        unset ROS_ETC_DIR
        unset ROS_PACKAGE_PATH
        unset ROS_ROOT
        unset ROS_MASTER_URI
        ```

    2. **Source the ROS 2 Foxy Setup Script:**
        ```bash
        source /opt/ros/foxy/setup.bash
        ```

    3. **Verify by Running a ROS 2 Node:**
        - In one terminal, start a C++ talker:
            ```bash
            ros2 run demo_nodes_cpp talker
            ```
        - In another terminal, start a Python listener:
            ```bash
            ros2 run demo_nodes_py listener
            ```

# Using Separate Terminals for ROS 1 and ROS 2

* **ROS 1 (Noetic):**
    ```bash
    source /opt/ros/noetic/setup.bash
    ```

* **ROS 2 (Foxy):**
    ```bash
    source /opt/ros/foxy/setup.bash
    ```
