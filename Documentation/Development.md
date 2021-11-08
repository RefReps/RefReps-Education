
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
### Configuring Environment
- Navigate to the root of the repository 
  - Run this command:
    - `npm install`
  - Create a `.env` file at the root of the repository
    - Copy the contents of the `.sample-env` file into the `.env` file and update the info as specified
    - *For testing purposes use the following address for DB_CONNECT:
      - `"mongodb+srv://sodadev:Mongodb123@cluster0.ocf1a.mongodb.net/myFirstDatabase?retryWrites=true&w=majority"`
    - Remove any square brackets
    - Put double quotes around values
### Running the API
- Navigate to the root of the repository
  - Run the command:
    - `npm run devStart`
    - application will refuse to execute if the `.env` file is not populated

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

## Test the App
- Go to the home page (`http://localhost:4200/home`)
- Select courses in the sidebar
- Two courses should be available:
  - Football 101
  - Basketball 101 
