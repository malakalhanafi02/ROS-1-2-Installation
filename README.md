# AI

1. Downloading Linux on MacOS
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


2. Preparing to download for ROS1:
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

3. Downloading ROS1 Noetic:
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










  
