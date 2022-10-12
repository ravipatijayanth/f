function guess_filenum {
	read guess
	if [[ $guess -eq $filenum ]]
	then
		echo "Amazing!!! YOU GUESSED !"
		echo "Hooooooray"
		echo "  SO WE HAVE ..."
		for f in $(ls)
		do
			echo "  - $f and "
		done
		echo "    ... AND THATS IT."
	else
		if [[ $guess -gt $filenum ]]
		then
			echo "THERE IS LESS... TRY AGAIN AND PRESS ON ENTER :"
			guess_filenum
		else
			echo "THERE IS MORE... TRY AGAIN AND PRESS ON ENTER:"
			guess_filenum
		fi
	fi
}
echo "WELCOME TO GUESS GAME!"
echo "GUESS HOW MANY FILES ARE IN THE CURRENT DIRECTORY AND PRESS THE ENTER BUTTON :"
guess_filenum
