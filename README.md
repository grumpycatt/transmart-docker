# A dockerfile in order to generate a tranSMART ready to go container

## Author
There is few versions and perceptions of this setup, here is the list of what I know :
* [QuartzBio](https://github.com/quartzbio/transmart-docker)
* [io-informatics](https://github.com/io-informatics/transmart-docker)

Here is another Dockerfile with an emphasis on best practices and performance regarding to tranSMART ecosystem.

Pull requests are welcome.

## Deployment
This is an all-in-one tranSMART setup thus it should not be used for production. The database, R, and Tomcat should be splitted in order to achieve a good througtput.

The amount of RAM is the critical part, at least 4GB should be assigned to the JVM for tranSMART to run properly, 10GB of disk free and 2VCPU are enough for the rest.

### How to start

#### Run the container from Docker Registry (easy)


#### Build and run on your own (advanced)
    git clone https://github.com/grumpycatt/transmart-docker.git
    cd transmart-docker
    docker build --rm --no-cache -t myrepo/transmart .
    docker run -d -p 8080:8080 myrepo/transmart


#### Debug and core components
* PostgreSQL 9.x
* Tomcat7
* Oracle JDK 1.8u45
* git
* tranSMART 1.2.x


    docker exec my_container ps axuf
