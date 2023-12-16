# ani-cli-batch
An Ani-cli wrapper written in BASH to simplify batch downloading multiple anime / seasons of the same anime

### Note
This script is just a wrapper for the ani-cli application developed by pystardust. You need to have the original ani-cli application installed to use this. Find it [here](https://github.com/pystardust/ani-cli)

## Installation
1. Install the dependencies

   - Head to [pystardust's ani-cli github](https://github.com/pystardust/ani-cli) and install it for your OS.
   - Install git (optional) (only if you want to use the ani-cli-batch-update feature to update the script)
   
3. Clone this repository locally

        git clone https://github.com/75rx/ani-cli-batch
   
4. Modify the shebang if you are on termux (see instructions below)
5. Give the scripts appropriate permissions

    chmod +x ani-cli-batch/ani-cli-*

6. Add the scripts to your PATH (modify this command accordingly if on termux (see instructions below))

        sudo mv -t /usr/local/bin/ani-cli-batch ./ani-cli-batch/ani-cli-*

7. Clean up the downloaded files

        rm -rf ani-cli-batch
   

### Instructions for termux users
#### Step-3
If you want to run this script on your android phone using termux, you will have to modify the shebang in the ani-cli-batch script. You can do that by opening the script using a text editor such as nano or vim and changing the first line to `#!/data/data/com.termux/files/usr/bin/bash`
or you can run this command

      sed -i s_\#\!\/usr\/bin\/env\ bash_\#\!\/data\/data\/com.termux\/files\/usr\/bin\/bash_g ./ani-cli-batch/ani-cli-batch
#### Step-5
 Add the scripts to your PATH. 
   - If you have a custom directory for your executables, simply move the ani-cli-batch script to that directory
   - If you do not have any such directory, just execute this command     

           mv ./ani-cli-batch/ani-cli-batch /data/data/com.termux/files/usr/bin


 WARNING: Do not use the ani-cli-batch-update command on your phone as it is not yet configured to run on termux. You can use the rest of the script normally
      
## Usage

Execute the script from a terminal and you'll be greeted with a query asking you what you want to download.

   ani-cli-batch

Once you answer it, the script will run ani-cli to search for your anime. After ani-cli finishes searching, it'll present you with a list of anime it found matching your search query.

DO NOT SELECT AN ANIME IN THIS LIST!

Instead, remember the position of your show in the list and exit the search results screen by typing exit or any other option that is not listed as a search result. Yes, I want you to crash the ani-cli script by entering an invalid choice.

The script will ask you to choose the correct selection in the next step. Type in the position / serial number of your anime from the previous screen.

## Uninstalling
On Linux

   sudo rm /usr/local/bin/ani-cli-batc*
   
On Android
   Remove the script from your PATH if you have added them into a custom folder in your PATH. If you followed this guide, then:

      rm /data/data/com.termux/files/usr/bin/ani-cli-batch

   You can also run `which ani-cli-batch` to see where the files are located and just delete them.


Follow the on-screen instructions and you will have added your anime to the download queue.


This is my first bash program. I know it isn't beautiful and the code requires better documentation but I wrote this for myself after watching 2 videos about bash scripting on youtube and then decided to share it online.
