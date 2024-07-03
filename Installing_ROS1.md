# Preparing to download for ROS1:
- Go to the Terminal in Linux, and follow these steps:
  1. Installing software-properties-gtk:
     ```sh
     sudo apt update
     sudo apt install software-properties-gtk
     ```
  2. Run:
     ```sh
     sudo software-properties-gtk
     ```
  3. From the window, ensure the following boxes are checked:
     - Canonical-supported free and open-source software (main)
     - Community-maintained free and open-source software (universe)
     - Proprietary drivers for devices (restricted)
     - Software restricted by copyright or legal issues (multiverse)
  - Make sure "Download from:" is set to "Main server" for the best availability of packages
  - After checking the necessary boxes, click "Close."

  ![Software Sources](https://github.com/malakalhanafi02/AI/assets/122760944/df154eb5-b6e9-44dc-ad6c-8df087e2cdd2)



# Installing ROS1 Noetic:

1. **Setup Your sources.list:**
    ```bash
    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
    ```

2. **Set Up Your Keys:**
    ```bash
    sudo apt install curl
    curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
    ```

3. **Update Package Index:**
    ```bash
    sudo apt update
    ```

4. **Install ROS Noetic:**
    ```bash
    sudo apt install ros-noetic-desktop-full
    ```

5. **Initialize rosdep:**
    ```bash
    sudo apt install python3-rosdep
    sudo rosdep init
    rosdep update
    ```

6. **Environment Setup:**
    ```bash
    echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
    source ~/.bashrc
    ```

7. **Install Additional Tools:**
    - Install rosinstall, a command-line tool for easily downloading ROS packages, and other necessary tools:
        ```bash
        sudo apt install python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
        ```

8. **Verifying Installation:**
    ```bash
    roscore
    ```
    If everything is set up correctly, you should see ROS core services start running, similar to the following output:
    <img width="670" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/4d0d94eb-66d7-482f-8425-673203465c28">
