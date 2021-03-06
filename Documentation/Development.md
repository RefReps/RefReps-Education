
# Development Environment Manual

## Docker-based Replication
 - Create an empty folder.
 - Open a terminal, navigate to your folder and run theses commands:  
   - `git clone https://github.com/hunterdurbin/refreps-back-end`
   - `git clone https://github.com/mkidd04/refprep-frontend` 
 - Download this [docker-compose file](https://github.com/mkidd04/RefReps-Education/blob/main/Auxiliary%20Files/docker-compose.yml), and put in the root of the folder you created
 - The root folder should look like this:
    - ![backend_tree](https://github.com/mkidd04/RefReps-Education/blob/main/Documentation/docker-root.png)
 - Open a terminal in the root the folder and run this command
   - `docker-compose up --build -d`
 - After anywhere from a few seconds to a few mintes of text scrolling across the screen, you should see:
   - `Creating frontend           ... done`
   - `Creating refreps_database_1 ... done`
   - `Creating backend            ... done`
 - After you see the above message, open a browser and go to http://localhost:4200/ or http://localhost/
   - You should see the green and white homepage
 - Experiencing problems?
   - ensure ports 3000, 4200, 27017, and 80 are open
   - ensure docker commands are run in the terminal at the folder you created for this project
  
 
## BACKEND (API)
### Install Prerequisites
- Install Node.js (v14.18.1 is tested)
  -  `https://nodejs.org/en/download/`
  -  Launch software after it finishes downloading
  -  Select:
      - **Run**
      - Welcome screen --> **Next**
      - License Agreement --> Agree --> **Next**
      - Installation location --> **Next**
      - Installation components --> Accept defaults --> **Next**
      - **Install**
      - **Finish**
- Install `nodemon`
  - Open command line 
  - Run this command:
    - `npm install -g nodemon`
### Clone Repository 
- Create an empty folder and clone this repository into that folder
  - Open command line
  - Run this command: 
    - `git clone https://github.com/hunterdurbin/refreps-back-end`
### File Structure
- Here is what the main file strucutre looks like
- ![backend_tree](https://github.com/mkidd04/RefReps-Education/blob/main/Documentation/backend-tree.png)

- public/
  - Houses static files that are used by the api.
  - Not mainly used for anything or core related to the api as of now
- src/controllers/
  - Makes responses from request for the `src/express-callback` to handle
- src/database/
  - Holds database information, such as model information
- src/express-callback/
  - Creates callbacks for express routers to use
- src/routers/
  - Catches http request and executes commands
  - Sends back responses to the client
- src/use-cases/
  - Holds base functionality for adding foundational features
- src/utils/
  - Holds extra utilities for the other directories to use
- uploads/ **Default location for uploads
  - Holds the downloaded files
  - This file location is dependent on the `.env` variable `LOCAL_UPLOAD_PATH`
- .env
  - File that must be created and content copied from `.sample-env`
- index.js
  - Main file to run the application


### Configuring Environment
- Navigate to the root of the repository 
  - Run this command:
    - `npm install`
  - Create a `.env` file at the root of the repository
    - Copy the contents of the `.sample-env` file into the `.env` file and update the info as specified
    - *For testing purposes use the following address for DB_CONNECT:
      - `"[DB URI]"`
    - Remove any square brackets
    - Put double quotes around values
### Running the API
- Navigate to the root of the repository
  - Run the command:
    - `npm run devStart`
    - application will refuse to execute if the `.env` file is not populated
    - see the README.md notes in the API repository for additional `.env` information
### Running Tests
- Navigate to the root of the repository
  - Run the command:
    - `npm test`
    - the application will test all files with `.spec` or `.test` using jest
    - code coverage will be shown and logged in the `/coverage` dir

## FRONTEND
### Install Prerequisites
- Install Angular CLI (v12.2.9 is tested)
  - Open command line
  - Run this command:
    - `npm install -g @angular/cli`
### Clone Repository 
- Create an empty folder and clone this repository into that folder
  - Open command line
  - Run this command: 
    - `git clone https://github.com/mkidd04/refprep-frontend`

### File Structure

![frontend-tree](https://user-images.githubusercontent.com/77707373/144947512-a841c14b-8605-437b-894d-0b5ca1febe81.jpg)


- /components
  - Houses the individual Angular components logic used in the application +
  - components.module.ts
    - typescript file where components are imported and need to be exported

- /models
  - Typescript files that model the data used in the backend api 

- /modules
  - a folder used to create components where multiple components are called 

- /shared/components
  - components which are shared throughout the whole application and show up in every page

- /app-routing.module.ts
  - the routes/path for the components to navigate 

- /service
  - houses the api calls used 




### Running the App
- Navigate to the root of the repository
  - Run the command:
    - `ng serve --open`
- The app should automatically open in a browser window

## Database (Mongodb)
### Install Prerequisites (for local database)
- If choosing to use a cloud database, preceed to the next step
- Install mongodb:
  - `https://www.mongodb.com/try/download/community`
  - Download v5.0.3 for your platform (msi installer is reccommended)
  - If prompted to download Mongo Compass, you may choose to do so if desired
    - (Mongo Compass is not required, but is better to quickly look at data)
  - If using default settings, your URI should be:
    - `mongodb://localhost:27017/<dbName>`
    - Where <dbName> is the name of your database
- Use this URI in the `.env` file for DB_CONNECT, or DB_TEST if for the test database

### Using Mongo Clusters (for cloud database)
- If using a local database, you may skip this step
- Sign up for a free account on `https://account.mongodb.com/account/login`
- After logging in:
  - Navigate on the left sidebar -> Deployment -> Databases
  - Click on `Create` located on the right of the screen
  - Click on `Shared` and choose the free tier, M0 Sandbox (Should be free for 1 Cluster)
  - The next few settings can be kept at default
  - Name the cluster
- Make a Database Access User
  - Naviage to Security -> Database Access
  - Click `add new database user`
  - Choose `Password` for the `Authentication Method`
  - Create a user and password
- Make a Network Access
  - Navigate to Security -> Network Access
  - Click `Add IP Address`
  - Choose `Add Current IP Address` to add your current IP address
  - Confirm
- Make a link to connect to the cluster:
  - Navigate back to Deployment -> Databases
  - Click on `Connect` in your cluster
  - For the `Setup connection security,` choose `Connect your application`
  - For `Choose a connection method,` choose `Driver = Node.js` and `Version = 4.0 or later`
  - You should now have a connection string for your application.
  - It should look something like this:
    - `mongodb+srv://<user>:<password>@<clusterName>.ocf1a.mongodb.net/<dbName>?retryWrites=true&w=majority`
    - Where <user> is your user for a user that has access to this cluster
    - <password> is the password for the user
    - <clusterName> is the name of your cluster
    - <dbName> is the database name in your cluster
- Use this URI in the `.env` file for DB_CONNECT, or DB_TEST if for the test database

## Test the App
- Go to the home page (`http://localhost:4200/home`)
- Select courses in the sidebar
- Two courses should be available:
  - Football 101
  - Basketball 101 
