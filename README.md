# ani-cli-batch
An ani-cli wrapper written in BASH to automate downloading different anime

### Note
This script is just a wrapper for the ani-cli application developed by pystardust. You need to have the original ani-cli application installed along with it's dependencies, to use this. Find it [here](https://github.com/pystardust/ani-cli)

## Installation

### Dependencies
1. ani-cli
2. wget
3. ani-cli's dependencies to run ani-cli. If you cannot install all of ani-cli's dependencies, at least try and get these:
    - grep
    - sed
    - curl
    - fzf
    - aria2c

### Windows

ani-cli-batch is a BASH script. You can provide your own BASH environment with all of the dependencies installed or you can simply follow this tutorial to set one up.

Fire up the windows terminal or a powershell window and run these commands

1. Install wsl
```
    wsl --install -d debian
```
Follow the on-screen prompts.
After the installation completes, close the terminal window, find an app called 'debian' in your start menu and launch it.

2. Install the dependencies

In the debian terminal:

    sudo apt update && sudo apt install grep sed curl wget fzf aria2 ani-cli -y

3. Download and configure this script
```
    wget https://raw.githubusercontent.com/75rx/ani-cli-batch/main/ani-cli-batch
    wget https://raw.githubusercontent.com/75rx/ani-cli-batch/main/ani-cli-batch-update
    chmod +x ./ani-cli-batch
    chmod +x ./ani-cli-batch-update
```
4. Move them to your PATH to access them from anywhere and enable the update functionality
```
    sudo mv -t /usr/local/bin ./ani-cli-batch ./ani-cli-batch-update
```
### Linux

1. Install the dependencies

Use your package manager to download and install the dependencies

a. On Debian / Ubuntu based systems like LinuxMint:

    sudo apt install grep sed curl wget fzf aria2 ani-cli -y

b. On RedHat based systems like Fedora and CentOS:

- Install ani-cli. The official installation method, after installing ani-cli's dependencies, according to pystardust's repository at the time of writing this documentation is:
```
    sudo dnf copr enable derisis13/ani-cli
    sudo dnf install ani-cli
```
- Install wget
```
    sudo dnf install wget
```
2. Download and configure the ani-cli-batch scripts
```
    wget https://raw.githubusercontent.com/75rx/ani-cli-batch/main/ani-cli-batch
    wget https://raw.githubusercontent.com/75rx/ani-cli-batch/main/ani-cli-batch-update
    chmod +x ./ani-cli-batch
    chmod +x ./ani-cli-batch-update
```
3. Move them to your PATH. Place them in /usr/local/bin to enable seamless updates with ani-cli-batch-update
```
    sudo mv -t /usr/local/bin/ ./ani-cli-batch ./ani-cli-batch-update
```
### Android

1. Download and install termux from [f-droid](https://f-droid.org/en/packages/com.termux/)

Warning: Do not install termux from the playstore. Termux's playstore builds are deprecated. If you cannot access f-droid, use [github](https://github.com/termux/termux-app/releases).

2. In termux, install the dependencies
```
    termux-change-repo
```
Then choose OK by pressing the enter key.

    pkg update && pkg install grep sed curl wget fzf aria2 ani-cli -y

3. Download and install ani-cli-batch
```
    wget https://raw.githubusercontent.com/75rx/ani-cli-batch/main/ani-cli-batch
    sed -i s_\#\!\/usr\/bin\/env\ bash_\#\!\/data\/data\/com.termux\/files\/usr\/bin\/bash_ ./ani-cli-batch
    chmod +x ./ani-cli-batch
    mv ./ani-cli-batch /data/data/com.termux/files/usr/bin
```
## Usage

### Adding anime to the download queue

1. Run the script in a terminal
```
    ani-cli-batch
```
2. Enter the name of the first anime you want to download after you are prompted for it.
3. ani-cli-batch will run ani-cli to search for your anime. Let ani-cli do it's job and wait until you have the search results
4. Remember the serial number / position of your anime in the search results list.
5. DO NOT select your anime from the search results. This will lead to ani-cli loading and downloading just that single anime. Instead, close ani-cli by pressing `CTRL`+`C` together, to get back to ani-cli-batch from ani-cli. You can also crash ani-cli by typing an invalid choice (eg: "exit" or "thisisdefinitelythenameofaverynormalanimethatexists") into ani-cli's textbox.
6. Enter the position / serial number of your anime from the previous screen, once you get back to ani-cli-batch
7. Follow the on-screen instructions to specify download quality and other information

### Updating the script

You can run `ani-cli-batch-update` on Windows and Linux to automatically update the script. Update functionality is not supported on android yet. So just follow the installation instructions again, i.e., copy paste these four lines of code into termux:

    wget https://raw.githubusercontent.com/75rx/ani-cli-batch/main/ani-cli-batch
    sed -i s_\#\!\/usr\/bin\/env\ bash_\#\!\/data\/data\/com.termux\/files\/usr\/bin\/bash_ ./ani-cli-batch
    chmod +x ./ani-cli-batch
    mv ./ani-cli-batch /data/data/com.termux/files/usr/bin

## Uninstalling

### On Windows

Run the following command in your wsl instance (the debian app if you followed this guide), to remove ani-cli-batch without uninstalling WSL or ani-cli.

    sudo rm /usr/local/bin/ani-cli-*

Refer to ani-cli's official repository for instructions on uninstalling ani-cli.

To remove everything completely (including WSL), go to Settings -> Apps, find Debian / WSL and uninstall it.

### On Linux

    sudo rm /usr/local/bin/ani-cli-*

Refer to ani-cli's official repository for instructions on uninstalling ani-cli.

### On Android

Simply uninstall Termux to get rid of everything, or `sudo rm /data/data/com.termux/files/usr/bin/ani-cli-batch` to remove ani-cli-batch from your termux environment.

Refer to ani-cli's official repository for instructions on uninstalling ani-cli.

Disclaimer: This software is in no way officially affiliated with ani-cli. It wasn't made by the developers of ani-cli. I'm also sorry about the poor code documentation. I wrote this for myself after barely watching a couple of BASH videos and -- on a whim -- decided to share it online.
