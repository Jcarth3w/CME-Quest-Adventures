# Development Environment Manual

## Frontend Installation (Godot Engine)

### Install Prerequisites

* Install Godot Engine (v4.1.1)
	* Download Godot [here](https://godotengine.org/download/archive/4.1.1-stable/)
	* Extract all from zip folder to somewhere accessible and easy to find.
	* Open Godot_v4.1.1-stable!

### Clone Repositories

* Open terminal and navigate to a place you'd like the project in.
* Type `git clone https://github.com/Jcarth3w/CME-Quest-Adventure.git`
* Open Godot_v4.1.1-stable
	* Click 'import' and navigate to where the project was cloned.
	* Go to 'project/project.godot' and double-click on it.
		* It should import and open the project automatically.
### Project File Structure
* Assets (png files for 2D objects)
* Objects (different types of interactables in the game)
* Scenes (visuals needed for game that don't fall under objects)

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

### Debugging the Game

* Open project within Godot.
	* Press 'F6' or the play button on the top-right.
	* Press 'F5' to test a currently selected scene.
