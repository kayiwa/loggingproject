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
  4. It will be important at the outset to determine the importance of restrospectively adding old logs v/s collecting real time logs

2. Project Justification and Benefits
  1. Benefits
    * Predictive decision making
    * Holistic view of post-mortems
    * Debugging of applications
    * Ability to safely get rid of some growing size of logs
    * Ease of use in comparing large datasets
  2. Justification
    The cost of logging is difficult to quantify. The reward of central logging generally comes at the most painful times. The ability to be able to allow more than just SSDR and USS staff in determining how systems are used is justification enough.

3. Strategy

  The goal here is to look into what tools are available on the market today that match the staffing at USS and SSDR. 

4. Scope

USS will set up an Elasticsearch, Logstash, Kibana (ELK) instance. The setup will include a Redis Server that will be a buffer between the logstash-forwarders and the logstash processor. USS will install a logstash-forwarder on a select number of servers after consulting with SSDR on what needs to be shipped.

  1. SSDR will accept responsibility of writing custom logstash filters in cases where their logs do not already have one. USS and SSDR will work on a way to limit who will have access to the Kibana interface. 
  2. The success of collecting all logs from one server will create a sub-project to select another server and move the successfully collected server up to staging and production.
  3. The project timeline would involve monthly cycles of selecting a server and ensuring the data can be collected from it. Selection of servers will be negotiated within the same timeline.

Other Resources.

Worth mentioning in this document. All of these services are offered by the companies like [Librato](https://librato.com) who offer a monthly free trial. UMD would to install a statsd or collectd agent to ship to the data to the librato server. The cost of these services is beyond the scope of this project but will need to be factored in as a cost-benefit analysis
