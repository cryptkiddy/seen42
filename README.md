# seen42
Small hack to automatically advance a counter of how many episodes of a series have been watched. Creates a markerfile in the folder named e.g. "seen42" and handles automatic advancement. Also easy selection and starting of the next episode is possible.

## usage
### Option 1

* put it in your path at e.g. "/usr/bin/seen" 
* make it executable ``` sudo chown 0:0 /usr/bin/seen; sudo chmod 755 /usr/bin/seen```
* 
* call it from the directory containing the episodes:
  * ```seen``` to advance counter by one or initially create it  
  * ```seen --open``` or ```seen o``` to automatically open the next episode and advance the counter if it was opened for more than 4 minutes (can be changed)  
  * ```seen --all``` after you have finished all episodes to set a "seenAll" marker  

### Option 2
  * Every ```seenXY``` marker is a copy of the script. Thus simply copying the script to e.g. "seen0" and executing with ```./seen0 --open``` will be fine, albeit cumbersome.
  
### settings

The script contains 3 settings variables to store basic settings:
* ```LIMIT=300 ```: sets the maximum number of episodes this script will work for. Does not really make a difference as long as it is higher than the highest numbered episode.
* ```PLAYER=smplayer```: sets the player used to play a file if ```seen --open``` is used. Must be blocking otherwise automatic advancement of counter will not work. Can be  more complex. Execution will be like ```$PLAYER $FILE_PATH```.
* ```SECONDS_TO_ASSUME_SEEN=240```: if player is open for less than the given number of seconds automatic counter advancement will not be triggered. (Only applies if ```seen --open``` is used)
