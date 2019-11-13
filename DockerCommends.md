Docker Hub URL
https://hub.docker.com/repositories

******************************
	BASIC
******************************
Publish : docker run -p 5000:5000 in28min/todo-rest-api-h2:1.0.0.RELEASE
          docker run -p 5005:5000 -d in28min/todo-rest-api-h2:1.0.0.RELEASE (if we use -d the application will not stop even if we close the terminal)

List of running containers
--------------------------
	docker container ls 
	docker container ls -a (shows stopped containers also)
	
Log viewing in -d container
---------------------------
	docker logs -f container
	
Stop the container
------------------
	docker container stop containerid
	
images List
-----------
docker images ls

http://192.168.99.100:5000/hello-world  (local host will not work with docker toolbox)

******************************
	IMAGES
******************************

tagging image
-------------
	docker tag in28min/todo-rest-api-h2:1.0.0.RELEASE in28min/todo-rest-api-h2:latest
	
Searching image
---------------
	docker search imagename (docker search todo-rest-api-h2)
pulling image to local
----------------------
	docker pull in28min/todo-rest-api-h2:1.0.0.RELEASE
	
history
-------
	docker image history imageid or repo/image:tag
	docker image history f8049a029560
	
inspect
-------
	docker image inspect imageid
	docker image inspect f8049a029560
	
remove from local
-----------------
	docker image remove imageid
	docker image remove c8ee894bd2bd

	
	
	
******************************
	Containers
******************************

Create
------
    both are same
	docker run -p 5005:5000 -d in28min/todo-rest-api-h2:1.0.0.RELEASE
	docker container run -p 5005:5000 -d in28min/todo-rest-api-h2:1.0.0.RELEASE
	
	--restart=always (even if the container is stopper on docker engine(demon) start this container also get started)
	--restart=no(Default value)
	docker container run -p 5006:5000 -d --restart=always in28min/todo-rest-api-h2:1.0.0.RELEASE
	
	-m 512m memory 
	--cpu-quota 5000      (100000(total) so allocate as required 5000 is 5%)
	
	docker container run -p 5005:5000 -m 512m --cpu-quota 5000 -d in28min/todo-rest-api-h2:1.0.0.RELEASE
	
Pause
-----
	Pause the container , u wont be ale to access the application if container is passed
	docker container pause containerid
	docker container pause f581f0
UnPause
-------
	docker container unpause containerid
	docker container unpause f581f0

Inspect
-------	
	docker container inspect containerid
	docker container unpause f581f0
	
	
Remove All stopped containers
-----------------------------
	docker container prune

Stop
----
	docker container stop containerid (graceful shutdown)
	docker container kill containerid (not graceful shutdown) immediately terminate the process
	
	

******************************
	STATS AND SYSTEM
******************************
	docker events  (what is happening in bagroud it keeps running until we kill the demon or terminal )
	docker top containerid (top process running in specific container)
	docker top e884
	docker stats  (all the stats reg container that are running)
	docker system df ( details of resources manage by docker demo)