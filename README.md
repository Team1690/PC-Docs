# Dev environemnt setup

# Terms 
 - Windows shell instances: (powershell/cmd) doesn't really matter which
 - WSL: a feature of Windows that allows developers to run a Linux environment without the need for a separate virtual machine
 - Fedora Remix: a linux distrobution

## Operating System setup
 - Download Vscode bt running `winget install -e --id Microsoft.VisualStudioCode` in a windows shell instance
 - Download the extension for vscode named WSL by pressing Ctrl+p, pasting this `ext install ms-vscode-remote.remote-wsl` and pressing enter
 - Ensure you have Windows Terminal installed by running `winget install microsoft.windowsterminal` in a windows shell instance
 - Run a windows shell instance as administrator (Right click should show a Run as administrator option) 
 - Install wsl with `wsl --install`
 - Download newest Fedora Remix WSL release by pressing the .msixbundle file in the Assets [here](https://github.com/WhitewaterFoundry/Fedora-Remix-for-WSL/releases)
 - Once the file is downloaded run the file and let the installer run
 - In the new **fedora** shell that opened enter your user name and password for the fedora account mkae the password memorable because you will write it alot
 - In a **fedora** shell change the wsl config by running the command below. After that enter your password. Every command that uses `sudo` will request a password, `sudo` means you want to run the command with elevated permissions. **when writing the password the letters aren't shown**
   - `printf '[interop]\nappendWindowsPath = false' | sudo tee -a /etc/wsl.conf` (This appends the string to a file)
 - Close all fedora terminal windows 
 - In a windows shell instance restart fedoraremix with the new configuration by running `wslconfig /t fedoraremix`
 - In a new fedora terminal (Use windows terminal to open a new terminal) update everything on your system with `sudo dnf upgrade -y` 
   - (`sudo` because this command needs elevated permission, `dnf` is the package manager, it helps you install, find and in this case `upgrade`  packages on your system (of course it does alot of other things), The `-y` flag means we want to accept everything installed without `dnf` asking)
 - Make sure fedoraremix is your default wsl distrobutions by running `wsl --set-default fedoraremix` in a **windows** shell instance
 - Make sure you are using WSL2 by running `wsl -l -v` (`-l`: list, `-v`: verbose) in a **windows** shell instance and make sure the vesion of `fedoraremix` is 2
 - You have finished downloading the Operating System!


## Git setup
 - Run the command `sudo dnf install git`
 - TODO: add SSH keygen explanation

## Flutter setup
 - Copy the link of the latest flutter release from [here](https://docs.flutter.dev/release/archive?tab=linux)
 - Run the command `wget https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_(CORRECT_VERSION_HERE)-stable.tar.xz`
    - You should paste the correct link (The one you copied) with Ctrl+Shift+v
 - Once the download finishes run the command `tar xf flutter_linux_(CORRECT_VERSION_HERE)-stable.tar.xz` 
    - You can find the exact file name with `ls`
 - Open Vscode and press the blue button in the bottom left corener and press Connect to WSL
 - Press Ctrl+o and open the /home/your_user_name/.bashrc file
 - Paste this to the bottom of the .bashrc file `export PATH="$PATH:/home/your_username/flutter/bin"`
 - Open a new terminal and run `flutter doctor`
 - You have officially Downloaded Flutter!

## Flutter native linux app setup
 - Run the command `sudo dnf install clang cmake ninja-build gtk3-devel`
 - Run `flutter doctor` again, now this should be written: [✓] Linux toolchain - develop for Linux desktop

## Flutter web app setup
 - Run these three commands 
  - `sudo dnf install fedora-workstation-repositories` 
  - `sudo dnf config-manager --set-enabled google-chrome` 
  - `sudo dnf install google-chrome-stable`
 - Run `flutter doctor` again, now this should be written: [✓] Chrome - develop for the web

## Flutter native android setup
 - TODO: when needed
