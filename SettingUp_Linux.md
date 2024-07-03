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
