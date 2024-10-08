# Elevator write-up

This is my first writeup so please be merciful

# Summary

This challenge was essentially an elevator style escape room in linux file architecture using bash commands to
navigate and search for the user info to advance to the next floor. The main commands used were su, grep, cd, ls, and cat. man can be used
for looking up function behavior, but isn't inherently required.

# Solution

First floor was simple enough, ls to find the user credentials folder, cd inm, then CAT the text file contents into the terminal.

Second floor was for me the most difficult through having to use the man command to learn all the options for grep. 
Using grep -r -l 'password' . was sufficient for searching for all the directories that contain passwords, I then picked one and
cat'd the output into the terminal.

Third floor was using grep to search for the specific keywords and output the contents pertaining to them.
grep 'password' creds_level3.txt and grep 'password' creds_level3.txt were my used commands in this one.

Fourth floor was a simple bash creds_level4.sh which output an interesting error message: 
=====creds:=====
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
next user: level4_26557 password: a8a86d
================

Fifth floor was a matter of using the correct command to identify all the folders, private or otherwise. ls -a worked for me to find both
the hidden folder and the hidden file. 

Sixth floor was a matter of using cd and cat on files with 'weird names' easy enough.

Seventh floor plopped you into vim, which required quitting vim and then returning to the root directory.

The eighth and final floor required going to the root directory and catting the contents of the flag.txt, capturing the flag. 

