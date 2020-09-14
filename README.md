# test-nodejs
1. Created 3 ec2 instance ( 1 master , 2 worker)
2. assigned elastic ip to master
3. installed docker, kubernetes on all nodes
4. install nodejs on master :     apt install node js 
5. create a directory (helloworld)
4. npm init       : to create package.json to hold the dependencies of the app
5. npm install express --save 		: to add express framework as first dependency
6. write a index.js file with a http server on port 8081	
7. node index.js    : in command prompt to run the app


8. created a docker file within the same project directory.
8a. FROM node:7					official node image
8b. WORKDIR /app   				set working directory in container to /app
8c. COPY package.json /app 			will copy package.json to the /app directory and the perform the npm install so that it doesn't dependencies again if changes are made to package,json file
8d. RUN npm install 				to install dependies
8e. COPY . /app					to copy application to /app directory
9.  CMD node index.js				to execute node index.js when the docker image is created.
10. expose 8081 				to expose port 8081 to the outside world.
11. docker build -t hello-world . 		to build the docker file 
12. docker run -p 8081:8081 hello-world 	to launch the docker image
13. docker build -t ajay946/hello-world . 	to build image again with docker hub credentials
14. docker login 				to login to dockerhub to push the image
15. docker push ajay946/hello-world 		to push the image to dockerhub	

16. kubectl create --namespace=test		created  a seperate namaespace in the cluster as test:
17. kubectl create -f deployment.yml -n test 	Deployed the deployment.yaml file in the test namespace
18. kubectl get pods -n test			to show the pods running
19. kubectl get deploy -n test 			to show the deployments
20. Have set the number of replicas as 2 in deployment file
