# battery4-inspired-sfz-drum-generator

Create battery4 style sfz drum presets on linux using bash and the systems dictionary. This script will search with in specified directories, shuffle and pick 49 wav samples and create a drum preset mapped much like NI bat4 across a 49 key controller.

Place this script in the root directory containing your sample folders. 

# IMPORTANT: 

directories as individual variables are setup for my environment and only map 49 keys. Can be modified. In order for this to work, you must rename the directories in this script to match the folders residing on same directory as script on your end. mine are,

script

d1="Kicks"

d2="Snares"

and so on.

if your kicks folder is called "hard-kicks" then in script, rename d1="Kicks" to d1="hard kicks" and so forth. This script uses the dictionary that ships with debian 12 to generate a random word for naming presets. The words or names can be a bit unusual. Also, presets will have a 3 digit # to prevent duplicates. A name like "Bat4-crumble-395.sfz" is what's to be expected.

To personalize your sfz, open script in text editor and copy replace 


CHAT_NF2BAT4BBE49_copy0


with your


preset name

save

quit

# Usage

mark as executable

chmod +x ./bat4-style-sfz-drum-preset-generator.sh

run from same directory containing sample pools

./bat4-style-sfz-drum-preset-generator.sh
