# Dev environemnt setup
## Operating System setup
 - Download Vscode from [here](https://code.visualstudio.com/)
 - Download the extension for vscode named: WSL (created by microsoft)
 - Download Windows Terminal from [here](https://www.microsoft.com/store/productId/9N0DX20HK701)
 - Run a powershell instance as administrator (Right click should show a Run as administrator option) 
 - Run the command `wsl --install`
 - Download newest Fedora release by pressing the .msixbundle file in the Assets [here](https://github.com/WhitewaterFoundry/Fedora-Remix-for-WSL/releases)
 - Once the file is downloaded run the file and let the installer run
 - In the new terminal enter your user name and password (remember your password it is very important!)
 - In the **fedora** terminal run `sudo bash -c 'echo -e "[interop] \n appendWindowsPath = false" >> /etc/wsl.conf'`
 - Close all fedora terminal windows 
 - In a **powershell** terminal run `wslconfig /t fedoraremix`
 - In a new fedora terminal (Use windows terminal to open a new terminal) run `sudo dnf upgrade` enter your password and wait (press y when they ask)
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
 - Run the command `sudo dnf install clang cmake ninja-build gtk3-devel`
 - Run `flutter doctor` again, now this should be written: [✓] Linux toolchain - develop for Linux desktop
 - You have officially Downloaded Flutter!

