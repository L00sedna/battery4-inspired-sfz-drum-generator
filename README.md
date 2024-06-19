# battery4-inspired-sfz-drum-generator
create battery4 style sfz drum presets.
This script will search with in specified directories, shuffle and pick 1 sample wav to your liking and create a drum preset mapped much like NI bat4.

Place this script in the root directory containing your sample folders.
IMPORTANT: directories as individual variables, are setup for my environment.
In order for this to work, you must rename the directories in this script to match the forlders residing on same directory as script on your end.
mine are, 

script

d1="Kicks"

d2="Snares"

and so on.

if your kicks folder is called "hard-kicks" then in script, rename d1="Kicks" to d1="hard kicks" and so forth.
This script uses the dictionary that ships with debian 12 to generate a random word for naming presets. The words or names can be a bit unusual. Also presets will have a 3 digit # to prevent dups. A name like "Bat4-crumble-395.sfz" is what's to be expected.
