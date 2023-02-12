# helloworld-flask-app
This is a Hello World web application written in Flask.

## Prerequisites
Below prerequisites must be fulfilled for successful execution of code.

### Software Requirement
Resources in this repository are meant for use with Python 3.x (check the version using `python3 --version`) and pip3 (check the version using `pip3 --version`). If you don't have the compatible version, download it from official python repository.

- [python3](https://www.python.org/downloads/) >= 3.9.2
- [pip3](https://pypi.org/project/pip/) >= 20.3.4

**Python Installation**
To install python3 and pip3 on ubuntu operating system using apt package manager, use below command.
```
    sudo apt update
    sudo apt install python3
    sudo apt install python3-pip
```

### Bootstrap Virtual Environment
It is a best practice to create a virtual environment for your application to avoid any conflict in dependencies between multiple applications. Hence, We will need to create a virtual environment (using python's default package "venv") and install all the dependencies.
```
python3 -m venv helloworld-app-venv # on Windows, use "python -m venv venv" instead
source helloworld-app-venv/bin/activate # on Windows, use "venv\Scripts\activate" instead
pip install -r requirements.txt
```

**Note:**
- Activation makes the virtual environment the default Python interpreter for the duration of a shell session. Because, This will prepend that directory to your PATH, so that running python will invoke the virtual environment’s Python interpreter. As an indication of virtual environment activation, current shell prompt will prepend the name of the virtual environment you are currently using.

- To deactivate the environment, simply type `deactivate` and you will return to your normal shell.

- Within the virtual environment, you can use the command `pip` instead of `pip3` and `python` instead of `python3`.

## Run and Test the App on Machine
To start the web server of the app, execute the below command -
```
    python run.py
```

To check the webapp, open a browser and go to URL -
```
    http://<IP>:Port
    http://127.0.0.1:8080/
```

## Run and Test the App on Docker
1. Clone the repository and switch inside the directory.
2. Build the docker image using below command: 
    `docker build . -t helloworld-app-img:latest`
3. To run the docker container from built image in the background with port mapping, use below command: 
    `docker run -d -p 5000:8080 --name helloworld-container helloworld-app-img`
4. To test the app on host machine, open the browser or use curl command: 
    `curl http://localhost:5000`

**Note:** 
- . tells docker about the path of the Dockerfile.
- Port mapping is used to access the services running inside a Docker container. In the above case, we can now access the application using port 5000 on the host machine.