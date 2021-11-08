
# Development Environment Manual
## BACKEND (api)
### Install Prerequisites
- Install Node.js (v14.18.1 is tested)
  -  https://nodejs.org/en/download/
  -  launch software after it finishes downloading
  -  Select:
    - **Run**
    - Welcome screen --> **Next**
    - License Agreement --> Agree --> **Next**
    - Installation location --> **Next**
    - Installation components --> Accept defaults --> **Next**
    - **Install**
    - **Finish**
- Install nodemon
  - Open command line 
  - Run this command:
    - npm install -g nodemon
### Clone Repository 
- Create an empty folder and clone this repository into that folder
  - Open command line
  - Run this command: 
    - git clone https://github.com/hunterdurbin/refreps-back-end
### Configuring Environment
- Navigate to the root of the repository 
  - Run this command:
    - npm install
  - Create a .env file at the root of the repository
    - Copy the contents of the .sample-env file into the .env file and update the info as specified
    - Remove any square brackets
    - Put double quotes around values
### Running the API
- Navigate to the root of the repository
  - Run the command:
    - npm run devStart
    - application will refuse to execute if the .end file is not populated

## FRONTEND
