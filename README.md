# Hydstra in the cloud discussion repository

The aim of this repository is:

1. To identify an appropriate model for cloud-based Hydstra software
2. To idenfity apprpriate administraion models for cloud-based Hydstra


## Client

* 1x HYCONFIG.INI per client.
* Each client needs an appstream with their specific config deployed
* So for each client, store HYCONFIG.INI in MONGO.db
* Have an aws cli script which deploys AppStream automatically. I.e. cutover from staging environment.

## Kisters

| System | Software | Description | OS | Est. Costs    | 
| :----------- | :---------- |  :---------- | ------ | ---------------| 
| Test Server  | Hydstra | 1 test install for all clients | Windows | | 

## Hydrological Data Services	

| System | Software | Description | OS | Est. Costs    | 
| :----------- | :---------- |  :---------- | ------ | ---------------| 
| Task Server  | AWS EC2 | Used for exe applications | Windows | | 
| Task Server  | Hydstra | Used for exe applications | Windows | | 
| Task Server  | PM2 | For running Hydstra exe tasks | Windows | | 
| Task Server  | nodejs webservice | For calling hyddlpx.exe | Windows | | 
| Task Server  | node-mailer | For emailing reports etc | Windows | | 
| AppStream    | AWS AppStream | For streaming Hydstra applicatiaon | Windows | | 
| AppStream    | Hydstra | Streamed app | Windows | | 
| Admin Server | Linux | runs deployement scripts (could be a desktop with bash stored in git) | Linux | |  
| db Server | Fedora machine | DigitalOcean VM | Linux | $5/mth |  
| db Server | PostGres/mongo/cassandra db | - |  Linux | $5/mth |  
| file Server | HDFS/S3 ?? | Used for Hydstra ts & documents | Linux? ||  


## Kisters: Hydstra Software As a Service

| Service        | 
| :------------- | 
| Cloud system hosted on AWS/microsoft whatever | 
| System & Database Backup |
| Disaster Recovery Plan |
| Manage Server Security | 
| Manage and Deploy Hydstra System Upgrades |
| Manage and Deploy Hydstra System Patches |
| Manage Multiple agency logins & active ActiveDirectory |
| Manage HYACCESS.INI to keep system running |
| Manage HYCONFIG.INI |
| Document the system including upgrades etc |
| **TOTAL HOSTING COST** |

* Adjust licensing fees appropriately for multiple agencies
* Include Hosting costs

![Deployment Diagram](https://www.lucidchart.com/publicSegments/view/5497b4a3-8d28-449a-9070-51a40a004901/image.png)



## Hydstra Administration Service 
### Outsourced or in-house

| Service        | 
| :------------- |
| HYAUDIT |
| HYGIENE |
| Standard maintenance & Admin tasks outlined in help file |
| Coordinate uptime/downtime with Kisters |
| Manage INIPATH & deploy non-Kisters scripts |
| Version control in GitHub/Bitbucket |
| Maintain Documentation in GitHub/Bitbucket |
| Provide first contact phone support |
| Maintain import-export & notification processors |
| Escalate to Kisters where support cannot be provided |
| **TOTAL ADMIN COST** |
