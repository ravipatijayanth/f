#!/usr/bin/env bash
filenum=$(ls | wc -l)

function guess_filenum 
{
	read guess
	
	if [[ $guess -eq $filenum ]]
	
	then
		echo "Amazing!!! You finally guessed it!"
		
		echo "Hooooray"
		echo "  SO WE HAVE ..."
		for f in $(ls)
		do
			echo "  - $f and "
		done
		echo "    ... and that was it."
	else
		if [[ $guess -gt $filenum ]]
		then
			echo "There is less... try again and press Enter :"
			guess_filenum
		else
			echo "There is more... try again and press Enter :"
			guess_filenum
		fi
	fi
}
echo "WELCOME TO GUESS GAME!"
echo "GUESS HOW MANY FILES ARE PRESENT IN CURRENT DIRECTORY and PRESS ON ENTER :"
guess_filenum
