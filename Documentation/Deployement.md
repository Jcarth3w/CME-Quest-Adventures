# Deployment Instructions

### NO SERVER IS NEEDED AT THIS TIME

## 1. Instiallation 

* Install Godot Engine (v4.1.1)
	* Download Godot [here](https://godotengine.org/download/archive/4.1.1-stable/)
	* Extract all from zip folder to somewhere accessible and easy to find.
	* Open Godot_v4.1.1-stable!

* Download zip folder from Github Repo [here](https://github.com/Jcarth3w/CME-Quest-Adventure)
  * Extract all from zip folder to somewhere accessible and easy to find.
  * Open Godot
    * Once prompted to open a project select the import option on the right
    * locate the extracted folder and select the folder labeled 'project'
   
## 2. Playing the game
  * Open project within Godot.
	  * Press 'F6' or the play button on the top-right.
	  * Press 'F5' to test a currently selected scene.
    * Press 'F8' while the game is running to stop gameplay.
   
## 3. Vulnerabilities 
  * The game does not perform well under heavy input. specifically in mini games.
  * Rapid clicks can cause games to potentially break. 

## 4. Troubleshooting
  * If experiencing any difficulties with the game occur:
    * Press 'F8' to exit the game and view the output error in the Godot terminal
    * Handle error accordingly

 ## 5. Testing
  * The testing for this project will be all handled within the plugin 'GUT' inside of the game engine.
    * On start-up of the game, located at the bottom of the terminal window GUT will be located.
    * Once you clicked into GUT, you can navigate to the test folders located in the FileSystem tree.
    * When you get to this point, you can choose any file if you want to test a singular file, or just run all the tests by clicking 'Run All'. If you choose to run a singular file, you can click the play button located in the 'Current:' prompt. You can also run a singular test within the chosen file too, by clicking onto the test function within the file and clicking that option in the 'Current: -> '.
    * You can also run all tests through the command line with this command below.
    * godot --headless -d -s --path project addons/gut/gut_cmdln.gd -gdir=res://tests/ -ginclude_subdirs=true -gprefix="" -gsuffix="_test.gd" -gexit
      * Notice, rename 'godot' to what you have Godot saved as the useable on your machine. Then you must specify this project path after '--path "Your Path"'.
    * After this is all complete, you should be able to start/stop/troubleshoot the project with testing purposes.
      
