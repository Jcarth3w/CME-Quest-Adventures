# Development Environment Manual

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

 
### Initialize Local Database
* In the main project repository, open up bash/terminal
* Execute `docker compose up`
* Launch your browser and go to `http://localhost:8000/`
	* If it fails, restart docker
		* Use `CTRL+C` to shutdown server
		* In Docker Desktop, click `STOP`
		* Close window
	* If database is empty, run `templateSql.sql` in an SQL IDE
		* In MySQL Community, login to server using credentials, and open the sql file to run/execute script
			* You can find your credentials in `docker-compose.yml`


    
### Project File Structure
* Addons (GUT testing framework)
* Assets (png files for 2D objects)
* Objects (different types of interactables in the game)
* Scenes (visuals needed for game that don't fall under objects)
* Tests (test scripts)


### Debugging the Game

* Open project within Godot.
	* Press 'F6' or the play button on the top-right.
	* Press 'F5' to test a currently selected scene.
