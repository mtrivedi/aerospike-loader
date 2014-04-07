#Aerospike Loader
Aerospike Loader is a tool to load formatted data in a file into aerospike server. This tool can load any third-party data in standard format like CSV Into aerospike server.

##Build
The code can be built with Maven. 
	
	mvn clean install

##Dependencies
* Aerospike Java client 3.0.22
* Apache commons cli 1.2
* Log4j 1.2.14
* Junit 4.4
* Json-simple 1.1.1

##Usage
The packaged Jar can be run with the following:
	java -jar aerospike-load-<version>.jar options filename(s)

###The options are:

	-c,--config <arg>                Column definition file name
	-ec,--abort-error-count <arg>    Error count to abort (default: 0)
	-et,--expiration-time <arg>      Expiration time of records in seconds (default: never expire)
	-h,--host <arg>                  Server hostname (default: localhost)
	-n,--namespace <arg>             Namespace (default: test)
	-p,--port <arg>                  Server port (default: 3000)
	-rt,--read-threads <arg>         Number of reader threads (default: Number of cores * 1)
	-s,--set <arg>                   Set name. (default: null)
	-T,--timezone <arg>              Timezone of source where data dump is taken (default: local timezone)
	-tt,--transaction-timeout <arg>  write transaction timeout in miliseconds(default: No timeout)
	-u,--usage                       Print usage.
	-v,--verbose                     Logging all
	-wa,--write-action <arg>         Write action if key already exists (default: update)
	-wt,--write-threads <arg>        Number of writer threads (default: Number of cores * 5)
	
##Example

	java -jar aerospike-load-<version>.jar -h 127.0.0.1 -p 3000 -n test -s demo -c src/test/resources/columns.json src/test/resources/data.csv
  
	The filename(s) can be a series of files and directories. 
  
##Documentation

	Check following link for how to use this utility and examples. 
	https://aerospike.atlassian.net/wiki/display/~jyoti/Aerospike+Loder?src=contextnavchildmode