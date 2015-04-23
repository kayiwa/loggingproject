# University of Maryland Libraries Log Project
## Library Servers Log Project
## Stashing Log Project

## Project Proposal
### Status: Draft

1. Positioning

   The goal of this project is to implement a way for User and Systems Support (USS) and Software Systems Development and Research (SSDR) to centrally collect logs from all servers. 

  1. The ability to have all the logs in one central place will aid both SSDR and USS to have a holistic picture of what the servers they use are doing. It will be an opportunity to be able to look at the impact of software development on hardware. It will enable and empower decision making in allocation of resources. Finally the ability to predict trends from aggregation of all hardware will help educate decision making.
  2. The project will involve players from SSDR and USS working in tandem in determining what logs are important to collect. The length of retention of data from production servers will need to be addressed. 
  3. The potential impact of this project is the amount of time that will be applied to write filters for non-standard logs. There will also be some time needed to install and configure the "shipper" of logs to the central server. The nature of this impact is impossible to determine a-priori. Some of servers run a version of Red Hat that does not have a ready shipper client. All Servers running Red Hat Linux 5.11 or lower will require a different mechanism to ship data to the central server. In addition to this problem the amount of data generated on the Central Server is impossible to determine a priori. There will be storage to determine and possible the creation of Elasticsearch and or Redis clusters to accommodate this. The selection of logging software therefore must be designed with scaling in mind. Finally the ability to restrict who can view these logs will need to be designed from the outset.

2. 
