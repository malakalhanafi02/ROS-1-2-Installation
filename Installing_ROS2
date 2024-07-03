# Installing ROS2 Foxy:

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
