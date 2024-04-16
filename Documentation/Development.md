# Development Environment Manual

## Tech aspects & Rundown

This project runs using Godot Engine 4 and includes a database using Firebase

In order to replicate this development environment you will need Godot Engine 4 and access to the firestore in Firebase

Godot does most of the heavy lifting, it runs the main game and is the main IDE we write code in

Firebase handles all of the data and can be accessed using any browser 

This document will guide you in installing and running these technologies as needed. This document also gives an in-depth look at the file structure of the project and will explain how to test/debug the code.


## Frontend Installation (Godot Engine)

### Install Prerequisites

* Install Godot Engine (v4.1.1)
	* Download Godot [here](https://godotengine.org/download/archive/4.1.1-stable/)
   		* Click "Show all downloads" in the bottom right
    ![Show all downloads](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/69c22091-f21c-401a-aa52-dae33a0ed014)
		* Select the correct version for your operating system
    ![osoptions](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/686bf8ff-2bcc-42f0-83d9-7ed48fc04594)

	* Unzip the downloaded file in a location that is easy to access
    ![downloaded](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/432d43b3-f4ba-4bb1-858b-f53b21481182)

	* Running the resulting executable will launch Godot_v4.1.1-stable



### Clone Repositories

* Open terminal and navigate to a place you'd like to store the project files.
	![Terminal](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/3e1cab26-5433-478e-ad10-efcec4b2bc76)

* Type `git clone https://github.com/Jcarth3w/CME-Quest-Adventure.git` (This will install the project files in your selected location)
* Open Godot_v4.1.1-stable
	* Click 'import' and navigate to where the project was cloned.
	![import](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/d9cacc69-bce2-4a08-bace-09d03bd4ba7b)

	* Go to 'project/project.godot' and double-click on it.
		* It should import and open the project automatically.
    
    ![Selectfile](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/4c8db880-aabf-47c1-b996-dd41304a382c)

 
### Accessing The Database

* Visit Firebase via any browser at this [url](https://firebase.google.com/?gad_source=1&gclid=CjwKCAjwoPOwBhAeEiwAJuXRh_Uv2oSatBiWhShDRH4jPds3rSuZyKPAOD8-rgtQ0B8W4P1zTjzzVxoCylEQAvD_BwE&gclsrc=aw.ds)
<img width="1424" alt="Screen Shot 2024-04-15 at 9 09 40 PM" src="https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/6a192e32-279e-4111-a26a-782fa92d5bcb">

* Click the "Get Started" button to view databases.
	* You should see a database labeled "CME-Quest-Adventures"
<img width="1417" alt="Screen Shot 2024-04-15 at 9 19 45 PM" src="https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/0626ff1e-6950-4ba7-b280-2c795647c084">
	* If you don't see this then you have not been added to the collection and must contact whoever is in charge or Jared Bowman @, the owner of the collection to add your email.

 * Once added you can view all data and use other tools that Firebase has to offer
<img width="1411" alt="Screen Shot 2024-04-15 at 9 26 16 PM" src="https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/04c8e88e-930e-44bf-9242-deef07998752">

    
### Project File Structure
#### Important files
* install_hooks.sh
  	* For installing the gdlint hook

#### Godot (project folder)
![files](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/3d2ed380-0536-45f5-8442-51d39df0f796)

* Addons (GUT testing framework/Firebase functionality)
* Assets (png files for 2D objects)
* Clickables (different types of interactables in the game)
* Components (gd scripts for sending HTTP requests to the Firebase
* Scenes (visuals needed for game that don't fall under objects)
* Tests (test scripts)


### Debugging the Game

* Open project within Godot

  ![play](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/f8d80bee-439f-4756-aadf-dfad3d62d022)

	* Press 'F6' or the play button on the top-right
	* Press 'F5' to test a currently selected scene
* Play through the game
	* If you run into an error the game will stop running and print an error via the output console in Godot
   	![debug](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/29b11144-4ce9-401d-aec5-4b0fdb15e978)

   * Otherwise, you may see unintended results within the game without a crash


### GDLint Integration
If you are wanting a tool that will guide you to cleaner code, follow these steps:
* Install [Python](https://www.python.org/downloads/) (if not done so already)
![download_python](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/11251881/75375586-24ea-4127-87b1-49844ee4bb45)

	* If there is a terminal process running, restart terminal.
* In terminal, run `pip install gdtoolkit==4.*` or `pip3 install gdtoolkit==4.*`

This will ensure that you have the necessary commands to run for the linter to work.

* Open the terminal within the project folder.
* Run `gdlint .`
	* Usage: `gdlint [target source]`
 ![Running_GDLint](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/11251881/936dbe98-b57e-4621-853f-8d12c60a591b)

This will check to see if the code within the folder is following a specific format. If there are any violations of the coding format, the command line will tell you what line needs work.

An alternative process is to:
* Go to the project folder.
* Double-click `install_hooks.sh`
![Install_hooks_location](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/11251881/2c993aeb-9cdd-4cd3-b1dc-6debb734df08)

	* This process includes the installation of python and gdlint.
	* This will also prevent any commits that violate the code structure of the project.
 
 ![Running_Hooks](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/11251881/290474c0-e904-41eb-90bf-ee8913ec37bb)


 ### How To Test

 * There are two ways to test this project
 	1. Running the game itself
  	2. Using GUT
  
## Testing by running
* To test by running the game, simply click the play button in the top right of Godot 
<img width="235" alt="Screen Shot 2024-04-15 at 9 34 59 PM" src="https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/ac4d7d9f-95a9-4cb3-86af-4e02ec07ab0c">

* To interpret this type of test, look for what you are trying to add/modify about the game.
	* Work within scenes to isolate specific things
 	* If something isn't behaving the way it should, take a look at the code


## Testing using GUT
<img width="972" alt="Screen Shot 2024-04-15 at 9 39 13 PM" src="https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/5f7fc525-fdda-4cbd-b936-08c4fcea0b98">

* Use the GUT tab at the bottom of the Godot IDE
	* Here you can chose to run individual test files or all of them

* Ensure the configuration runs all scripts with the prefix "test_"  and suffix ".gd" or else the tests will not run
 	* Click on a test function in a script to select the individual test for running. 

* Results of tests should either pass or fail depending on their expected outcome
	*  Remember what your looking for while testing
 	*  Ensure you understand what exactly you are testing  


