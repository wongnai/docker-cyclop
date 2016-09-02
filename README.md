#Cyclop in Docker

Dockerized cyclop using built web from https://github.com/maciejmiklas/cyclop

Cyclop is WEB UI for exploring cassandra cluster.

##Start a container
To start a container, just execute the following command. 
 
	docker run --name cyclop -d --net=host --restart=always wongnai/cyclop
 
After starting the container, you should be able to access cyclop at http://localhost:8080 . 
 
##Environment Variables
The default configuration assumes that the cassandra cluster is on the same host.
If you want to point to remote host, change the following variables:-

	cassandra_hosts=localhost
    cassandra_port=9042
    
To run a container with environment variables, execute the command:-

	docker run --name cyclop -d --net=host --restart=always \
		-e cassandra_hosts=mycassandra -e cassandra_port=9042 \
		wongnai/cyclop
