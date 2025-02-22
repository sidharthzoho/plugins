# Mongodb Monitoring
                                                                                              
## Prerequisites

- Download and install the latest version of the [Site24x7 Linux agent] / [Site24x7 Windows agent] (https://www.site24x7.com/app/client#/admin/inventory/add-monitor) in the server where you plan to run the plugin. 
---

### Plugin Installation  

- Create a directory named "mongod" under the Site24x7 Linux Agent plugin directory: 

		Linux             ->   /opt/site24x7/monagent/plugins/mongod
      
- Download all the files in the "mongod" folder and place it under the "mongod" directory.

		wget https://raw.githubusercontent.com/site24x7/plugins/master/mongod/mongod.py
		wget https://raw.githubusercontent.com/site24x7/plugins/master/mongod/mongod.cfg

- Execute the following command in your server to install pymongo: 

		pip install pymongo

- Execute the below command with appropriate arguments to check for the valid json output:

		python mongod.py --host=<host_name> --port=<port_number> --username=<username> --password=<password> --dbstats=<dbstats> --replset=<replset> --dbname=<dbname>


---

### Configurations

- Provide your MongoDb configurations in mongod.cfg file.

		["mongodb"]
		host=<host_name>
		port=<port_number>
		username=<your_username>
		password=<your_password>
		dbstats=<dbstats>
		replset=<replset>
		dbname=<dbname>
		
The agent will automatically execute the plugin within five minutes and send performance data to the Site24x7 data center.
