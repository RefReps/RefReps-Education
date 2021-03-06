# Docker Deployment

## Local Machine Deployment
- For a local computer deployment, follow the steps from Docker-based Replication in Development documentation
  - https://github.com/mkidd04/RefReps-Education/blob/main/Documentation/Development.md#docker-based-replication
- The application will automatically build the client side as a SPA web page, launch the api, and setup a mongodb
- Port forward port 80 on your machine to deploy the application

# Manual Deployment

## Deploying the API

### Manually Starting the Node Server

- Download the latest release version from https://github.com/hunterdurbin/refreps-back-end/releases
- Move the directory on the machine to host the API applicaiton
  - Can be a local machine or server hosting such as AWS, DigitalOcean, etc...
- Navigate to the root of the directory
- Prepare the dependecies by running `npm install` at the root
- Create the `.env` file at the root of the directory
  - Populate the `.env` with the `.sample-env`
  - Note that the application will refuse to run if the `.env` file is not populated
  - Include an uploads folder to correspond with the LOCAL_UPLOAD_PATH
  - More information to setup the `.env` file can be found in the API README.md
- Start the server with `npm run start`
- When stopping the server, either kill the terminal process, or use ctrl+C

## Deploying the Frontend

### Manually Deploying the Frontend

- QUICK LOCAL DEPLOYMENT
- To run the dev version of the application, download the latest release source from https://github.com/mkidd04/refprep-frontend/releases
- run `ng serve` at the root of the application
- It should host on `localhost:4200`

###
- OFFICIAL DEPLOYMENT
- Download the latest release version from https://github.com/mkidd04/refprep-frontend/releases
  - To build a new distribution, run `ng build` on the root directory for the repository 
- Download the dist file
  - This folder holds the static index file
  - This is a SPA and a pushState application
- Move the dist dir on the machine to host the API application
- Use an application that can host static, pushState files

## Setting up the Database (Mongodb)

- Reference the development documentation to setup a deployment for the mongodb
  - https://github.com/mkidd04/RefReps-Education/blob/main/Documentation/Development.md#database-mongodb
- Make sure to use your database URI as the DB_CONNECT `.env` variable in the node `.env` file
