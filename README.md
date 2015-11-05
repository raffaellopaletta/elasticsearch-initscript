Elastic Search SystemV init script 
==================================
A SysV init script for [Elastic Search](https://www.elastic.co/downloads/elasticsearch).

## Installation

#### Copy files and set permissions

```
$ sudo cp etc/init.d/elasticsearch /etc/init.d/
$ sudo cp etc/default/elasticsearch /etc/default/
$ sudo chmod a+x /etc/init.d/elasticsearch
```

#### Edit files 

edit */etc/init.d/elasticsearch* file according to your Elastic Search configuration

```
$ sudo vim /etc/init.d/elasticsearch

...

ES_HOME="/usr/local/share/elasticsearch-2.0.0" 	# Elastic Search home
ES_RUN=$ES_HOME/run								# Elastic Search pid files path
ES_LOGS=$ES_HOME/logs							# Elastic Search log files path
MAX_NODES=3	

```

edit */etc/default/elasticsearch* file according to your java configuration

```
$ sudo vim /etc/default/elasticsearch

...

PATH=`echo $PATH:/usr/java/jre1.7.0_03/bin`
```

#### Use init script

##### Start service (an instance of ES)
```
$ service elastaticsearch start 
Starting elasticsearch...                         [OK] (pid=30498)
```

##### View service status
```
$ service elasticsearch status
Checking elasticsearch...                         2 Nodes running
                                                  NODE PID=30498
                                                  NODE PID=30741
```

##### Stop service (all instances of ES)
```
$ service elastaticsearch stop 
Stopping elasticsearch... 
Process 30498 killed
Process 30741 killed

```

## License

(MIT License)

Copyright (c) 2015 Raffaello Paletta <raffaellopaletta@gmail.com>

This is open source software, licensed under the MIT License. See the file LICENSE for details.
