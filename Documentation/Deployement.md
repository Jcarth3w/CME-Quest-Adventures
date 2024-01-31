# Deployment Instructions


## 1. Installation 

* Install Godot Engine (v4.1.1)
	* Download Godot [here](https://godotengine.org/download/archive/4.1.1-stable/)
	* Extract all from zip folder to somewhere accessible and easy to find.
	* Open Godot_v4.1.1-stable!

* Download zip folder from Github Repo [here](https://github.com/Jcarth3w/CME-Quest-Adventure)
  * Extract all from zip folder to somewhere accessible and easy to find.
  * Open Godot
    * Once prompted to open a project select the import option on the right
    * locate the extracted folder and select the folder labeled 'project'

## 2. Server

* There is a small web server attached to the game for managing database operations
	* This can be run locally at any time or can be hosted through a service such as Google Cloud
   
## 3. Playing the game
  * Open project within Godot.
	  * Press 'F6' or the play button on the top-right.
	  * Press 'F5' to test a currently selected scene.
 	* Press 'F8' while the game is running to stop gameplay.
   
## 4. Vulnerabilities 
  * The game does not perform well under heavy input. specifically in mini-games.
  * Rapid clicks can cause games to potentially break.
  * Frequent pausing and unpausing of the game can also result in unwanted errors.

## 5. Troubleshooting
  * If experiencing any difficulties with the game occur:
    * Press 'F8' to exit the game and view the output error in the Godot terminal
    * Handle errors accordingly

* If experiencing any difficulties with the server:
   * Shut down the server
   * Take note of server error
   * Reboot the server

 ## 6. Testing
  * The testing for this project will be handled within the plugin 'GUT' inside of the game engine.
    * On start-up of Godot, located at the bottom of the terminal window GUT will be located.
      
      <img width="571" alt="Screen Shot 2023-12-08 at 7 36 29 PM" src="https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/27f47219-b07f-471c-8bf1-eb1f48ee0850">

    * Once you've clicked into GUT, you can navigate to the test folders located in the FileSystem tree.
      
	<img width="206" alt="Screen Shot 2023-12-08 at 7 37 19 PM" src="https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/84037a64-d77f-49a8-9468-1ad717151a9f">


    * When you get to this point, you can choose any file if you want to test a singular file, or just run all the tests by clicking 'Run All'. If you choose to run a singular file, you can click the play button located in the 'Current:' prompt. You can also run a singular test within the chosen file too, by clicking on the test function within the file and clicking that option in the 'Current: -> '.

 	<img width="540" alt="Screen Shot 2023-12-08 at 7 38 14 PM" src="https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/c87a14ab-6724-4e12-8799-6e2f79b5f219">



    * You can also run all tests through the command line with this command below.
    * godot --headless -d -s --path project addons/gut/gut_cmdln.gd -gdir=res://tests/ -ginclude_subdirs=true -gprefix="" -gsuffix="_test.gd" -gexit
      * Notice, rename 'godot' to what you have Godot saved as the useable on your machine. Then you must specify this project path after '--path "Your Path"'.
    * After this is all complete, you should be able to start/stop/troubleshoot the project for testing purposes.
      
