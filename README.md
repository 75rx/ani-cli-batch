# ani-cli-batch
An Ani-cli wrapper written in BASH to simplify batch downloading multiple anime / seasons of the same anime

### Note
This script is just a wrapper for the ani-cli application developed by pystardust. You need to have the original ani-cli application installed to use this. Find it [here](https://github.com/pystardust/ani-cli)

## Installation
1. Head to [pystardust's ani-cli github](https://github.com/pystardust/ani-cli) and install it for your OS.
2. Clone this repository locally

        git clone https://github.com/75rx/ani-cli-batch
   
3. Modify the shebang if you are on termux (see instructions below)
4. Add the script to your PATH

    sudo mv ./ani-cli-batch/ani-cli-batch /usr/local/bin/ani-cli-batch
   
6. Clean up the downloaded files

    rm -r ani-cli-batch
   

### Instructions for termux users
If you want to run this script on your android phone using termux, you will have to modify the shebang in the script. You can do that by opening the script using a text editor such as nano or vim and changing the first line to `#!/data/data/com.termux/files/usr/bin/bash`
or you can run this command

      sed -i s_\#\!\/usr\/bin\/env\ bash_\#\!\/data\/data\/com.termux\/files\/usr\/bin\/bash_g ./ani-cli-batch/ani-cli-batch
      
## Usage

Execute the script from a terminal and you'll be greeted with a query asking you what you want to download.

Once you answer it, the script will run ani-cli to search for your anime. After ani-cli finishes searching, it'll present you with a list of anime it found matching your search query.

DO NOT SELECT AN ANIME IN THIS LIST!

Instead, remember the position of your show in the list and exit the search results screen by typing exit or any other option that is not listed as a search result. Yes, I want you to crash the ani-cli script by entering an invalid choice.

The script will ask you to choose the correct selection in the next step. Type in the position / serial number of your anime from the previous screen.

Follow the on-screen instructions and you will have added your anime to the download queue.

### Note

The downloader is currently experiencing problems so asking this script to directly download the entire download queue will result in a failure. However, there is a very simple solution you can temporarily use to work around this problem. After you've finished adding all of your anime to the download queue, print out the download command using the script's menu, copy it and execute it as you would any other command.

# To-Do

- [ ] Fix the script's downloader and get rid of the workaround
- [ ] Write a complimentary script to check for, and manage updates

This is my first bash program. I know it isn't beautiful and the code requires better documentation but I wrote this for myself after watching 2 videos about bash scripting on youtube and then decided to share it online.
