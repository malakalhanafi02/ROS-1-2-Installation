# 🚀 Welcome to the Ultimate Guide: Running Ubuntu, Linux, ROS1 Noetic, and ROS2 Foxy on your Mac with UTM! 🛠️

⭐️ What You’ll Achieve:
- UTM installed and ready to virtualize.
- A fully operational Ubuntu system running smoothly on your Mac.
- Both ROS1 (Noetic) and ROS2 (Foxy) set up and ready for action.
- The ability to toggle between ROS1 and ROS2 environments like a pro. 🧑‍💻

# 1. Downloading Linux on MacOS
- Download UTM: [UTM Download](https://mac.getutm.app/)
- Download Ubuntu 20.04 (image): [Ubuntu 20.04 Download](https://cdimage.ubuntu.com/releases/20.04.5/release/)
- Open UTM:
  - "Create a New Virtual Machine" -> “Virtualize” -> “Linux” -> "Boot ISO image" -> (choose the Ubuntu 20.04 image you downloaded)
  
  ![UTM Setup](https://github.com/malakalhanafi02/AI/assets/122760944/2424b7b3-e308-45cb-bbff-cd4a58a1c381)
  
  - Allocate the required resources (half of your system’s resources) to the machine:
      - e.g., for a Macbook Pro M2 with Memory 16GB, CPU Cores: 8, use: _Memory 6144MB, CPU Cores: 4, Storage: 80GB_
  - Add a Share directory "Downloads" -> "Name: Ubuntu 20.04" -> "Create" -> "Start"
  
  ![UTM Settings](https://github.com/malakalhanafi02/AI/assets/122760944/0d8b5584-8e62-48bd-9392-e5cc3f444639)
  
  - Follow the instructions (English -> Continue without updating -> Keyboard configuration "done" -> Proxy (most home networks don't use a proxy) -> Mirror address (Don't change) "Done"
  - Storage "use the entire disk"
  
  ![Ubuntu Disk Setup](https://github.com/malakalhanafi02/AI/assets/122760944/61b695e5-2413-4737-b1de-cb6b346a26d3)
  
  - "Continue" -> Set up Ubuntu profile -> Install OpenSSH or skip
  - Now the installation starts!!
  - "Cancel update and reboot"
  
  ![Ubuntu Reboot](https://github.com/malakalhanafi02/AI/assets/122760944/3f42369f-a67d-4e82-8513-0773f22c683d)
  
  - We want to clear this, so go to the setting icon (top right corner, ![Settings Icon](https://github.com/malakalhanafi02/AI/assets/122760944/608a2e9b-1ed8-46aa-881b-431fc3cb7219)) and click clear path:
  
  ![Clear Path](https://github.com/malakalhanafi02/AI/assets/122760944/73c1da54-80fd-4327-b903-0155a2e841f1)
  
  - After that, click play & login using your credentials.
- Installing the Desktop Environment:
  - Run:
    ```bash
      sudo apt install kubuntu-desktop
    ```
- After installation process has completed successfully, reboot your system `sudo reboot`, login using your credentials

<p style="font-size:100px;">🎉DONE!🎉</p>

  ![Desktop Installed](https://github.com/malakalhanafi02/AI/assets/122760944/7db63381-e349-48d6-ab31-4ce8b7c02d8f)

# 2. Preparing to download for ROS1:
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

# 3. Installing ROS1 Noetic:

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

# 4. Installing ROS2 Foxy:

1. **Set locale (Check for UTF-8 locale):**
    ```bash
    locale  # check for UTF-8
    ```

2. **Update and install locales:**
    ```bash
    sudo apt update && sudo apt install locales
    sudo locale-gen en_US en_US.UTF-8
    sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
    export LANG=en_US.UTF-8
    ```

3. **Verify the locale settings:**
    ```bash
    locale
    ```
    <img width="241" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/b13713e6-0d3c-403a-8880-551fb57b9f7d">

4. **Setup Sources:**
    - Ensure that the Ubuntu Universe repository is enabled:
        ```bash
        sudo apt install software-properties-common
        sudo add-apt-repository universe
        ```

5. **Add the ROS 2 GPG key with apt:**
    ```bash
    sudo apt update && sudo apt install curl -y
    sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
    ```

6. **Add the repository to your sources list:**
    ```bash
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
    ```

7. **Install ROS 2 Packages:**
    - Update your apt repository caches:
        ```bash
        sudo apt update
        ```
    - Upgrade your system:
        ```bash
        sudo apt upgrade
        ```
    - Install ROS 2 Foxy Desktop:
        ```bash
        sudo apt install ros-foxy-desktop python3-argcomplete
        ```

8. **Environment Setup:**
    - Source the setup script:
        ```bash
        source /opt/ros/foxy/setup.bash
        ```

9. **Verify Installation of ROS 2 Foxy:**
    - You should see a list of installed ROS 2 Foxy packages:
        ```bash
        dpkg -l | grep ros-foxy
        ```

# Troubleshooting

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



  
