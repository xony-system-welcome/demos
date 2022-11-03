https://hevodata.com/learn/docker-postgresql/

https://medium.com/quick-code/how-to-run-postgresql-and-pgadmin-using-docker-90638fde8bf

##### Take the Docker PostgreSQL image. Open a new command window, and run the command given below.
```
docker pull postgres
```

##### To obtain the list of existing Docker Images, run the following command.
```
docker images
```

##### In the next step, you can enter the command you copied from the Docker Hub in the Command Prompt.
```
docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres
```
Output：80822dbd8ecd75ddff6b589422553be91553c1473dfd950f1339cc2a996585e4

##### The above-given command should be customized and added with the necessary parameters to work properly for setting up PostgreSQL on Docker.
```
docker run --name postgresql -e POSTGRES_USER=myusername -e POSTGRES_PASSWORD=mypassword -p 5432:5432 -v /data:/var/lib/postgresql/data -d postgres
```
Output：4220631f978d776f84638879860956b98fc41f1cf77108bdcb638db0cc739b66

###### In the command given above, 
PostgreSQL is the name of the Docker Container.<br>
* **-e POSTGRES_USER** is the parameter that sets a unique username to the Postgres database.<br>
* **-e POSTGRES_PASSWORD** is the parameter that allows you to set the password of the Postgres database.<br>
* **-p 5432:5432** is the parameter that establishes a connection between the Host Port and Docker Container Port. In this case, both ports are given as 5432, which indicates requests sent to the Host Ports will automatically redirect to the Docker Container Port. In addition, 5432 is also the same port where PostgreSQL will be accepting requests from the client.<br>
* **-v** is the parameter that synchronizes the Postgres data with the local folder. This ensures that Postgres data will be safely present within the Home Directory even if the Docker Container is terminated.<br>
* **-d** is the parameter that runs the Docker Container in the detached mode, i.e., in the background. If you accidentally close or terminate the Command Prompt, the Docker Container will still run in the background.<br>
* **postgres** is the name of the Docker image that was previously downloaded to run the Docker Container.<br>

Now, execute **docker ps -a** to check the status of the newly created PostgreSQL container. <br>
docker ps -a to check the status
```docker ps -a```

* For starting the Docker Container:
```docker start postgresqldb```

* For stopping the Docker Container:
```docker stop postgresqldb```




##### Install PGAdmin on Docker
At this stage of setting up the Docker PostgreSQL Environment, your PostgreSQL is active and running on the respective ports. Now, you have to install the PGAdmin, a web-based GUI tool used to manage PostgreSQL databases and services. You can install PGAdmin to check whether your Docker Containers are working fine and execute SQL queries on databases present in PostgreSQL.<br>

To download PGADmin, perform these steps: <br>

* Visit Docker Hub and search for PgAdmin. You can find various Docker Images to run PGAdmin. Select the appropriate one and copy the Docker pull command (Follow this link **https://hub.docker.com/r/dpage/pgadmin4** to get the “Docker pull” command, which pulls the PGAdmin4 version. You can also get the respective PGAdmin versions according to your preferences). <br>
* Execute the pull command to start PGAdmin.<br>
>If error "Error response from daemon: Get "https://registry-1.docker.io/v2/": x509: certificate has expired or is not yet valid: current time " you need to set the NTP
```docker pull dpage/pgadmin4:latest```

* After downloading the image, run the container by executing the command given below.<br>
```docker run --name my-pgadmin -p 82:80 -e 'PGADMIN_DEFAULT_EMAIL=user@domain.local' -e 'PGADMIN_DEFAULT_PASSWORD=postgresmaster'-d dpage/pgadmin4```

In the above-given command, **my-pgadmin** is the name of the Docker PostgreSQL PGAdmin Container. **PGADMIN_DEFAULT_EMAIL** and **PGADMIN_DEFAULT_PASSWORD** are the username and password for the Docker PostgreSQL container, respectively.
