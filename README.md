# How to setup a single node (master) cluster in Apache Spark

#### First check hosts in your local machine
- sudo vim /etc/hosts
- you can use the localhost IP-address to run your master node

#### Install dependencies
- apt install java
- apt install scala

#### Install Apache Spark
- wget https://dlcdn.apache.org/spark/spark-3.3.2/spark-3.3.2-bin-hadoop2.tgz
- tar xvf spark-3.3.2-bin-hadoop2.tgz

#### Move the extracted spark to a relevant directory
- mv spark-3.3.2-bin-hadoop2 /etc/opt/spark

#### Set-up the environment for the Spark by editing bashrc file
- vim ~/.bashrc
- add the following commands to bashrc file
- export SPARKHOME=/etc/opt/spark
- export PATH=$SPARKHOME/bin:$SPARKHOME/sbin
- activate the changes by the running the command -> source ~/.bashrc
- cd /etc/opt/spark
- vim spark-env.sh
- add the following command to spark-env.sh file → export SPARK_MASTER_HOST=’127.0.0.1’

#### Run the following commands to start the cluster and master node
- start-master.sh
- browse 127.0.0.1:8080 or localhost:8080(as configured in hosts name list) to see master node page

#### Note
- You can also add multiple worker nodes on same machine locally with the command -> start-worker.sh <master-url> 



