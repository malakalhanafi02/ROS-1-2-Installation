# AI

# 1. Downloading Linux on MacOS
- Download UTM: https://mac.getutm.app/
- Download Ubuntu 20.04 (image): https://cdimage.ubuntu.com/releases/20.04.5/release/
- Open UTM:
  "Create a New Virtual Machine" -> “Virtualize” -> “Linux” -> "Boot ISO image" -> (choose the Ubuntu 20.04 image you downloaded)
  
 <img width="271" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/2424b7b3-e308-45cb-bbff-cd4a58a1c381">
 
  -> (Allocate the required resources (half of your system’s resources) to the machine) ex. Memory 6144MB, CPU Cores: 4, Storage: 80GB
  -> (Add a Share directory "Downloads") -> "Name: Ubunto 20.04" -> "Create" -> "Start"
  ->
  <img width="573" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/0d8b5584-8e62-48bd-9392-e5cc3f444639"> 
  
  -> Follow the instructions (English -> Continue without updating -> keyboard configuration "done" -> Proxy (most home networks don't use a proxy) -> Mirror address (Dont change) "Done" -> 
  
  Storage "use the entire disk" -> <img width="916" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/61b695e5-2413-4737-b1de-cb6b346a26d3"> 
  
  "Continue" -> Set up Ubuntu profile -> Install OpenSSH or skip -> Now the installation starts!!
  "Cancel update and reboot" 
  <img width="812" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/3f42369f-a67d-4e82-8513-0773f22c683d">
We want to clear this, so go to the setting icon (top right corener, <img width="33" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/608a2e9b-1ed8-46aa-881b-431fc3cb7219">) and click clear path: <img width="1137" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/73c1da54-80fd-4327-b903-0155a2e841f1">.

After that, click play & login using your credentials.
- Installing the Desktop Environment:
  RUN "$ sudo apt install kubuntu-desktop"
- After installation process has completed successfully, reboot your system "sudo reboot", login using your credentials

  DONE!<img width="1271" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/7db63381-e349-48d6-ab31-4ce8b7c02d8f">


# 2. Preparing to download for ROS1:
- Go to the Terminal in Linux, and follow these steps:
  1. Installing software-properties-gtk:
'sudo apt update
 sudo apt install software-properties-gtk'
  2. Run 'sudo software-properties-gtk'
  3. From thw windoq, ensure the following boxes are checked:
  - Canonical-supported free and open-source software (main)
  - Community-maintained free and open-source software (universe)
  - Proprietary drivers for devices (restricted)
  - Software restricted by copyright or legal issues (multiverse)
    Select Main Server:
  - Make sure "Download from:" is set to "Main server" for the best availability of packages
After checking the necessary boxes, click "Close."
     <img width="1033" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/df154eb5-b6e9-44dc-ad6c-8df087e2cdd2">

# 3. Installing ROS1 Noetic:
  1. Setup Your sources.list: RUN sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
  2. Set Up Your Keys: sudo apt install curl
                       curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
  3. Update Package Index: sudo apt update
  4. Install ROS Noetic: sudo apt install ros-noetic-desktop-full
  5. Initialize rosdep: sudo apt install python3-rosdep
                        sudo rosdep init
                        rosdep update
  6. Environment Setup: echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
                        source ~/.bashrc
  7. Install Additional Tools:
       - Install rosinstall, a command-line tool for easily downloading ROS packages, and other necessary tools:
         sudo apt install python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
  8. Verifying Installation: roscore
     If everything is set up correctly, you should see ROS core services start running, similar to the following output:<img width="670" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/4d0d94eb-66d7-482f-8425-673203465c28">

# 4. Installing ROS2 Foxy:
1. Set locale (Check for UTF-8 locale): 
locale  # check for UTF-8

2. Update and install locales:
sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

3. Verify the locale settings:
locale

<img width="241" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/b13713e6-0d3c-403a-8880-551fb57b9f7d">


Setup Sources

4. Ensure that the Ubuntu Universe repository is enabled: 
sudo apt install software-properties-common
sudo add-apt-repository universe

5. Add the ROS 2 GPG key with apt:
sudo apt update && sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

6. Add the repository to your sources list:
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

Install ROS 2 Packages

7. Update your apt repository caches:
sudo apt update

8. Upgrade your system:
sudo apt upgrade

9. Install ROS 2 Foxy Desktop:
sudo apt install ros-foxy-desktop python3-argcomplete

Environment Setup

10. Source the setup script:
source /opt/ros/foxy/setup.bash

Verify Installation of ROS 2 Foxy
11. You should see a list of installed ROS 2 Foxy packages: 
dpkg -l | grep ros-foxy

* If you get this error message: <img width="1238" alt="image" src="https://github.com/malakalhanafi02/AI/assets/122760944/9c6b8644-3b5a-4e64-981e-5691c2c4ed55">
Follow these steps:
1. Clear Previous ROS Environment Variables:
unset ROS_DISTRO
unset ROS_ETC_DIR
unset ROS_PACKAGE_PATH
unset ROS_ROOT
unset ROS_MASTER_URI

2. Source the ROS 2 Foxy Setup Script:
source /opt/ros/foxy/setup.bash

3. Verify by Running a ROS 2 Node:
- In one terminal, start a C++ talker:
ros2 run demo_nodes_cpp talker
- In another terminal, start a Python listener:
ros2 run demo_nodes_py listener


* Using Separate Terminals for ROS 1 and ROS 2:
- ROS 1 (Noetic): source /opt/ros/noetic/setup.bash
- ROS 2 (Foxy): source /opt/ros/foxy/setup.bash













  
