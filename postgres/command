###Take the Docker PostgreSQL image. Open a new command window, and run the command given below.
'''
docker pull postgres
'''

###To obtain the list of existing Docker Images, run the following command.
'''
docker images
'''

###In the next step, you can enter the command you copied from the Docker Hub in the Command Prompt.
'''
docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres
'''
Output：80822dbd8ecd75ddff6b589422553be91553c1473dfd950f1339cc2a996585e4

###The above-given command should be customized and added with the necessary parameters to work properly for setting up PostgreSQL on Docker.
'''
docker run --name postgresql -e POSTGRES_USER=myusername -e POSTGRES_PASSWORD=mypassword -p 5432:5432 -v /data:/var/lib/postgresql/data -d postgres
'''
Output：4220631f978d776f84638879860956b98fc41f1cf77108bdcb638db0cc739b66

####In the command given above, 
PostgreSQL is the name of the Docker Container.
-e POSTGRES_USER is the parameter that sets a unique username to the Postgres database.
-e POSTGRES_PASSWORD is the parameter that allows you to set the password of the Postgres database.
-p 5432:5432 is the parameter that establishes a connection between the Host Port and Docker Container Port. In this case, both ports are given as 5432, which indicates requests sent to the Host Ports will automatically redirect to the Docker Container Port. In addition, 5432 is also the same port where PostgreSQL will be accepting requests from the client.
-v is the parameter that synchronizes the Postgres data with the local folder. This ensures that Postgres data will be safely present within the Home Directory even if the Docker Container is terminated.
-d is the parameter that runs the Docker Container in the detached mode, i.e., in the background. If you accidentally close or terminate the Command Prompt, the Docker Container will still run in the background.
postgres is the name of the Docker image that was previously downloaded to run the Docker Container.

/n
Now, execute docker ps -a to check the status of the newly created PostgreSQL container. /n
docker ps -a to check the status
'''
docker ps -a
'''
