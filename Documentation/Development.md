
# Development Environment Manual
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

![file structure api](https://github.com/mkidd04/RefReps-Education/blob/main/Documentation/api-structure.png)
- public/
  - Houses static files that are used by the api.
  - Not mainly used for anything or core related to the api as of now
- routers/
  - Catches http request and executes commands
  - Sends back responses to the client
- schemas/
  - Holds the structure of how each entity is made
  - Uses mongoose to create schemas
- server/
  - Creates the express application
- test/
  - Holds all of the test
  - Matches the file structure of the root repository
- uploads/ **Default location for uploads
  - Holds the downloaded files
  - This file location is dependent on the `.env` variable `LOCAL_UPLOAD_PATH`
- utils/
  - Holds extra utilities for the other directories to use
  - Some include db querying, connection creating, validation, etc
- .env
  - File that must be created and content copied from `.sample-env`
- server.js
  - File that makes the express application listen on a port
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
