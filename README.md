# ani-cli-batch
An Ani-cli wrapper to simplify batch downloading multiple anime / seasons of the same anime

### Note
This script is just a wrapper for the ani-cli application developed by pystardust. You need to have the original ani-cli application installed to use this. Find it [here](https://github.com/pystardust/ani-cli)

## Installation
1. Head to pystardust's ani-cli github and install it for your OS.
2. Clone this repository locally
3. Use a text editor of your choice to edit the shebang in the main script, ani-cli-batch.sh. If you do not know what this means, just remove the first line in ani-cli-batch.sh.
4. (Optional but recommended) rename ani-cli-batch.sh to anime and add it to your PATH.

## Usage

Execute the script from a terminal and you'll be greeted with a query asking you what you want to download.
Once you answer it, the script will run ani-cli to search for your anime. After ani-cli finishes searching, it'll present you with a list of anime it found matching your search query.
DO NOT SELECT AN ANIME IN THIS LIST! Instead, remember the position of your show in the list
