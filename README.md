# Hydstra in the cloud discussion repository

The aim of this repository is:

1. To identify an appropriate model for cloud-based Hydstra software
2. To idenfity apprpriate administraion models for cloud-based Hydstra

Thoughts on setup
=================

## Architecture & responsibilities


### Client

* 1x HYCONFIG.INI per client.
* Each client needs an appstream with their specific config deployed
* So for each client, store HYCONFIG.INI in MONGO.db
* Have an aws cli script which deploys AppStream automatically. I.e. cutover from staging environment.

### Kisters

* Test (Windows license? Y) (Est. Cost)
** Hydstra - only one test install for all clients 


### Hydrological Data Services	

* Administration Server
** Linux which runs deployement scripts after an update
** Or can we just do this from a dev machine with the scripts stored in Git?

* TaskServer (Windows license? Y)
** Hydstra
** PM2 for monitoring & spawning Hydstra apps
** nodejs webservice
** hymailer to email issues

* AppStream (Windows licence? Y)
** Hydstra 

* Linux Fedora machine (DigitalOcean? Y $5/mth)
** PostGres/mongo/cassandra db 

* AWS S3 - Linux HADOOP??
** Hydstra ts & documents


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
