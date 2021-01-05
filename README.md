### 1. Background

Name of the Project: Docker challenge  
Context of the project: BeCode, Liège Campus, AI/Data Operator Bootcamp, January 2021  
Objective: learning (images, containers, volumes)  
Author: Frédéric Fourré  
Email: fourrefrederic593@gmail.com  


### 2. The mission

Reproduce the following architecture:

```
/app
    |-docker
    |   |-Dockerfile -> your Dockerfile
    |-pipeline
    |   |
    |   |-model
    |   |    |-model.py -> print a number between 1 and 400
    |   |-preprocessing
    |   |    |-preprocessing.py -> print a numpy array
    |   |-utils
    |   |    |-utils.py -> print "in progress..."
```


Steps:

1. Create a github repository
2. Create the above directory structure in it
3. Create a Dockerfile that copy those files in an `/app` folder and run the `model.py` file
4. Build your image
5. Run a container and verify that it prints the ouput of your `model.py` file
6. Connect to your container with SSH and run all the python files `model.py`, `preprocessing.py`, `utils.py`
7. Stop you container and delete it *(check that there are no more containers running with `docker container ls -a`)*
8. Run a new container using a volume to do changes without stopping the container and saving your changes. Connect to SSH so it stays running
9. Add two lines of code in each files locally (be creative !)
10. Re-run all your python files to verify that the changes are effective in your container
11. Delete all your **containers** and **images**
12. Push your repo with your Dockerfile


### 3. Some commands used to solve the challenge

`sudo docker build . -t model:v1.1`  
`sudo docker run -t model:v1.1`  
`sudo docker stop $(sudo docker ps -a -q)`  
`sudo docker rm $(sudo docker ps -a -q)`  
`echo $PWD`  
`sudo docker run -v $PWD:/app -it model:v1.1 bash`  
`cat model.py`  
`python3 utils.py`  











