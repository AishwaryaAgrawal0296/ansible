### RHSM Setup

- To subscribe a system to Redhat statellite following steps are followed . 
    - shell script subscribeToSatellite.sh is used for subscribing the box to Redhat statellite . 
	- if the box is already subscribe to Redhat statellite then subscribeToSatellite.sh script will unregister the box and register it again.
	- subscribeToSatellite.sh script supports on following OS distribution.
	 	- Centos 6
	 	- Centos 7
		- Redhat 6
	 	- Redhat 7
	- After the successfull excution of subscribeToSatellite.sh script , system update is done to update system packages and then system is attached to the required pool for required package installation.
	- For the docker setup  and registerting the system to Redhat Statellite(Redhat 7 and Centos 7)  ansible playbook * rhsm-register-docker-install.yml*  is used.
> rhsm-register-docker-install.yml playbook call the roles that are required for registration and docker setup

| S.no 	| Role Name 	| Purpose 	|
|------	|---------------------	|--------------------------------------------------------------------------------------------------------------------------------	|
| 1 	| rhsm-registration 	| It subscribes  the system to Redhat Statellite on the basis of OS distribution Box has 	|
| 2 	| rhsm-update-system 	| Checks the system kernal version and update the sytem and display the updated the kernal version 	|
| 3 	| rhsm-docker-install 	| Attach the system to the docker pool , install the docker-ce , start the docker service and display the docker service status| 	|
