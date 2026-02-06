# Simple Web Application

This is a simple web application using [Python Flask](http://flask.pocoo.org/)  For Docker Image build LAB.
It has two part . First implement and test the Part1 and next go to part2 

Part1
Create a small web flask application and run it directly from EC2 instance . Access the web site from browser 

Part 2
containerize the previously created small web flask application and run it from container . Access it from browser .

.....................................................................................................................................................................
Part1
Create a small web flask application and run it directly from EC2 instance . Access the web site from browser 

  Below are the steps required to get this working on a base linux system Ec2 inatnce .
  
  - **Install all required dependencies**
  - **Install and Configure Web Server**
  - **Start Web Server**
   
## 1. Install all required dependencies
  
  Python and its dependencies
  ```bash
#Install Python & Pip #
yum update -y 
yum install python3 -y 
yum install python3-pip -y

#verify the version #
python3 --version 
pip3 --version 
```
   
## 2. Install and Configure Web Server

Install Python Flask dependency
```bash
#Install Flask #
pip3 install flask 
```

## 3.Copy `app.py` or download it from a source repository to current dir /root

## 4. Start Web Server
```bash
 python3 app.py
```

## 5. Start Web Server.

Open a browser and go to URL
```
http://<EC2 pub IP>:5000                           
http://<IP>:5000/how%20are%20you            
```

# Part 2
# containerize the previously created small web flask application and run it from container . Access it from browser .

## 1.login as root [sudo su - ] Install Docker on EC2 
````
Install Docker on EC2 

sudo yum install docker -y 

sudo systemctl start docker 

sudo systemctl enable docker 

sudo usermod -aG docker ec2-user 

newgrp docker 

docker --version
````
## 2.Create requirements.txt in current directory i.e /root 
```
vi requirements.txt 
Flask
```
## 3.Create app.py in /root with github code app.py
```
https://github.com/Dev664/simple-web-app/blob/master/app.py
```
## 4.Create Dockerfile in /root  from github Dockerfile 
```
```
## 5.Build Image 
```
docker build -t flask-dev .
```
## 6.Run Container 
```
docker run -d -p 5000:5000 --name flask_container flask-dev
```

