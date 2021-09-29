# Comandos

cf push --random-route

cf set-env 12-dogs DOG_BREED spaniel
cf set-env 12-dogs DOG_SUBBREED cocker

cf restage 12-dogs

cf marketplace

cf marketplace -e postgresql-db
cf marketplace -s postgresql-db

cf create-service postgresql-db trial dog-db
cf bind-service 12-dogs dog-db

cf create-service-key dog-db db-key
cf service-key dog-db db-key

cf allow-space-ssh bootcamp-dev
cf enable-ssh 12-dogs
cf restart 12-dogs

netstat -a

50490

cf ssh -L 50490:postgres-97c87b8a-31e7-427e-b710-e14dd65e3f09.ce4jcviyvogb.eu-central-1.rds.amazonaws.com:3735 12-dogs

psql -d TvQIMXtFLrSq -U 045e750937c2 -p 50490 -h localhost


SELECT * FROM dog_collection

Use the following command to horizontally scale your app. Cloud Foundry will increase or decrease the 
number of instances of your app to match INSTANCES
cf scale 12-dogs -i 3
cf app 12-dogs




# 12-dogs-app
[![License: Apache2](https://img.shields.io/badge/License-Apache2-green.svg)](https://opensource.org/licenses/Apache-2.0)

## Description  
Sample [12-factor app](https://12factor.net/) implementation to run on SAP Business Technology Platform (cloud foundry)

This application can be deployed also on a Local Machine (for development purposes)

## Requirments
*  [Install the Cloud Foundry CLI](https://developers.sap.com/tutorials/cp-cf-download-cli.html)
*  [Learn the Fundamentals of SCP Cloud Foundry](https://developers.sap.com/tutorials/cp-cf-fundamentals.html)

## Deployment
**STEP 1** - Download or Clone this repository

**STEP 2** - Navigate to the directory you cloned and Push the app to Cloud Foundry
```bash
cf push --random-route
```
**STEP 3** - Set the environment variables using the following command. 
```bash
cf set-env 12-dogs DOG_BREED spaniel
cf set-env 12-dogs DOG_SUBBREED cocker
```

**STEP 4 ** - Create the DB service Instance
```bash
cf marketplace
** TO DO ** 
```

**STEP 5** - Restart the app
```bash
cf restart 12-dogs
```

**STEP 6** - Run the app on the **route** displayed in the terminal

## Support and Contributions
This repository is provided "as-is". No support is available. Feel free to open issues or provide pull requests.

## License
This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES) file.
