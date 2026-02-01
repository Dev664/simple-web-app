# Simple Web Application

This is a simple web application using [Python Flask](http://flask.pocoo.org/) and [MySQL](https://www.mysql.com/) database. 
This is used in the demonstration of the development of Ansible Playbooks.
  
  Below are the steps required to get this working on a base linux system.
  
  - **Install all required dependencies**
  - **Install and Configure Web Server**
  - **Start Web Server**
   
## 1. Install all required dependencies
  
  Python and its dependencies
  ```bash
sudo yum update -y 

sudo yum install python3 -y 

sudo yum install python3-pip -y 

python3 --version 

pip3 --version 
  ```
   
## 2. Install and Configure Web Server

Install Python Flask dependency
```bash
pip3 install flask 
```

- Copy `app.py` or download it from a source repository
- Configure database credentials and parameters
  ```bash
mkdir flask-app 
cd flask-app 
```
  

## 3. Start Web Server

Start web server
```bash
docker run -d -p 5000:5000 --name flask_container flask-dev
```

## 4. Test

Open a browser and go to URL
```
http://<EC2 pub IP>:5000                           
http://<IP>:5000/how%20are%20you            
```
