[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/qg4qXfSB)
This is my attempt of Assignment 2 for Distributed Systems class.
I am trying to farm commits for now and figuring out how to handle this assignment.
Admittedly, it is not going well yet. I am trying to work on it but I have to prepare for the midterm. (which did not end well, admittedly)

Update, 27.10.23, 20:40, next to D107:
I suppose I have solved the 80% part with the given credentials as evidenced by the logs I have uploaded. I might try the 100% part and delete 80%. I will also upload the docker file too.
I uploaded the configuration file from Docker Engine too just to be sure. 

Here are the steps I followed to create a container containing a database (more information is available in logs I have shared):

I pulled the image using the pull command;
I used "docker run -d --name postgres_container -p 5432:5432 -e POSTGRES_PASSWORD=dist_pass_123 postgres" to create a container on 5432 with the given credentials;
I verified the creation with "docker ps", which returned:
CONTAINER ID   IMAGE      COMMAND                  CREATED          STATUS          PORTS                    NAMES
68c38f9ea395   postgres   "docker-entrypoint.s…"   29 seconds ago   Up 27 seconds   0.0.0.0:5432->5432/tcp   postgres_con;
I executed the container using "docker exec -it postgres_container bash";
I used "psql -h localhost -U postgres" to run psql;
I created a database called "my_db" and filled in the fields as such:
"CREATE TABLE ASYNC_MESSAGES (RECORD_ID SERIAL PRIMARY KEY, SENDER_NAME VARCHAR(30), MESSAGE VARCHAR(30), SENT_TIME TIMESTAMP, RECEIVED_TIME TIMESTAMP);"
I used " SELECT * FROM my_db;" to see my table is correct;
And I created a user with the given credentials again, so that I could connect using PSQL.
Running it locally, everything works as it should, but admittedly, using university wi-fi and trying to connect using different machines of the fellow students yielded in problems that we are still trying to solve, for more than 3 days now. We cannot establish connection even though we have cross-checked I will make sure that I submit / commit the latest / best version, my best effort, basically. This has been a hectic yet interesting introduction to Docker and containers in general. 

Update (29.10.23, 22:28:28): 
I tried different tutorials and other methods that I can think of, but none yielded in tangible results. I believe I will stick with the version I have right now: at least it works on my machine. I tried my best and allocated far more time than I thought I would need, but I agree that I could have and should have done better. In any case, I would like to get what I was doing wrong / how it can be fixed. 


