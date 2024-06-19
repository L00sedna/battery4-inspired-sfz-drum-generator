#!/bin/bash

# Declare directories as individual variables. 
d1="Kicks"
d2="Snares"
d3="Claps"
d4="Percussion/Sticks"
d5="Percussion/Tambs"
d6="HiHats"
d7="Vocals"
d8="looping_hats"
d9="OpenHiHats"
d10="Cymbals, Crashes, and Rides"
d11="Basses"
d12="Snares/Rolls"
d13="Percussion"
d14="Stabs, Hits & Oneshots"
d15="Subs"

# Array of directories in 49key keyboard order 
directories=(
# key 36-42
  "$d1" "$d1" "$d2" "$d3" "$d4" "$d5" "$d6"
# key 43-49
  "$d7" "$d6" "$d8" "$d9" "$d10" "$d1" "$d11"
# key 50-55
  "$d2" "$d12" "$d4" "$d13" "$d6" "$d14"
# key 56-62
  "$d6" "$d8" "$d9" "$d10" "$d1" "$d1" "$d2"
# key 63-69
  "$d3" "$d4" "$d13" "$d6" "$d14" "$d6" "$d8"
# key 70-77
  "$d9" "$d10" "$d1" "$d11" "$d2" "$d3" "$d15" "$d5"
# key 78-84
  "$d6" "$d14" "$d6" "$d8" "$d9" "$d10" "$d11"
)

# Create a temporary file
TMP_FILE=$(mktemp -q /tmp/sfz.XXXXXX || exit 1)
n=36

# Function to find and shuffle a file from a directory
find_and_shuffle() {
  local dir=$1
  find "$dir" -type f | shuf -n 1
}

# Write SFZ regions directly to the final file
SFZ_FILE=$(mktemp -q /tmp/sfz_final.XXXXXX || exit 1)
{
  for dir in "${directories[@]}"; do
    sample=$(find_and_shuffle "$dir")
    echo -e "<region> key=$n sample=$sample"
    n=$((n+1))
  done
} > $SFZ_FILE

# Generate a random name
randomname() { shuf -n1 /usr/share/dict/words; }
RANDOM_WORD=$(randomname)
SFZ_FILENAME="Bat4-${RANDOM_WORD}-$((RANDOM % 999 + 100)).sfz"
mv "$SFZ_FILE" "$SFZ_FILENAME"

# Set traps to clean up files
trap 'rm -f -- "$TMP_FILE"' EXIT

# Continue with script
echo "sfz is ready: ${SFZ_FILENAME}"

# Clean up logic
rm -f -- "$TMP_FILE"
trap - EXIT
exit
