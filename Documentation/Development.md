# Development Environment Manual

## Tech aspects & Rundown

This project runs using Godot Engine 4 and includes a web server backend using Docker, PHP, and MySQL

In order to replicate this development environment you will need Godot Engine 4, Docker, an SQL IDE (**SQL WORKBENCH RECOMENDED**) and an IDE (**VS CODE RECOMMENDED**)

Godot does most of the heavy lifting, it runs the main game and is the main IDE we write code in

Docker helps us run backend code and our web server, we edit these files using an IDE of our choice

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

* Install Docker
	* Download Docker [here](https://docs.docker.com/engine/install/)
 	* Select the correct version for your operating system 
   
![dock](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/316def0a-bc49-47eb-a523-3fa2144224c9)

* Click the download button to download the Docker installer
 
![yuh](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/2a8fd99d-a2bf-4364-a42c-455fd0f862e0)

* Run the installer and follow it's instructions to open Docker
![install](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/7ffead15-e208-4e85-8fe0-9c7ec3a9c526)




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

 
### Initialize Local Database
* In the main project repository, open up bash/terminal
* Make sure Docker is running
![shell+docker](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/632dc41b-838d-45f6-90a1-2b8a5a08c167)


* Execute `docker compose up`
* The result of this command should look like this
* This command creates a Docker container where the web server and data base run
  ![running](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/bfd99b6d-92d0-4e6d-a472-9b88b0901efc)

  
* Launch your browser and go to `http://localhost:8000/`
  ![loacalhost](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/a2757766-3062-43cd-9015-7735de5eb245)

	* If it fails, restart docker
		* Use `CTRL+C` to shutdown server
		* In Docker Desktop, click `STOP`
		* Close window
	* If database is empty, run `templateSql.sql` in an SQL IDE
		* In MySQL Community, login to server using credentials, and open the sql file to run/execute script
			* You can find your credentials in `docker-compose.yml`


    
### Project File Structure
#### Important files
* docker-compose.yml/Dockerfile
	* These files describe the rules for creating the Docker container
*  templateSql.sql
  	* This file is the template for creating the database which Docker takes care of
* install_hooks.sh
  	* For installing the gdlint hook

#### Godot (project folder)
![files](https://github.com/Jcarth3w/CME-Quest-Adventures/assets/89651665/3d2ed380-0536-45f5-8442-51d39df0f796)

* Addons (GUT testing framework)
* Assets (png files for 2D objects)
* Clickables (different types of interactables in the game)
* Components (gd scripts for sending HTTP requests to the web server)
* Scenes (visuals needed for game that don't fall under objects)
* Tests (test scripts)

#### Webserver
* Contains all php files for sending and recieving data


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
