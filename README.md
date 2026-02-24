# Devops Task - Containerization & Deployemnt of Full-stack Mean Application
## Step 1: Repository Setup
Create New repositroy name - mean-devops-project
Now in Vscode Open the Application folder and push the code by the following commands:
* -git init
* -git add .
* -git commit -m "Initial commit"
* -git branch -M main
* -git remote add origin https://github.com/Arthisuresh210/mean-devops-project.git
* -git push -u origin main
<img width="1907" height="970" alt="git" src="https://github.com/user-attachments/assets/0dd48bc5-1f91-44fa-a606-7685d01717df" />


## Step 2: Containerization & Deployment
* In the backend folder add Dockerfile and write the dockerfile for backend
* Similarly for frontend
* Build the docker image by following commands:
* -docker build -t arthisuresh0210157/backend ./backend
  <img width="1370" height="624" alt="docker-backend" src="https://github.com/user-attachments/assets/f2276b9c-7b8d-48bb-af32-1d283bed0e80" />

  

* -docker build -t arthisuresh0210157/frontend ./frontend
<img width="1425" height="721" alt="docker-frontend" src="https://github.com/user-attachments/assets/c2e3b0cb-2445-4214-a4bd-32c67eafe35d" />


## Push the image to Docker Hub
* -docker login
  <img width="1206" height="318" alt="docker login" src="https://github.com/user-attachments/assets/947505e3-989f-4eca-8b89-87e47bf33300" />
* -docker push arthisuresh0210157/backend

<img width="1235" height="447" alt="build-backend" src="https://github.com/user-attachments/assets/83386f1b-b6c4-43fe-baaa-8d6db4bffdc8" />

* -docker push arthisuresh0210157/frontend

<img width="1251" height="385" alt="build-frontend" src="https://github.com/user-attachments/assets/7d74aaba-2e52-4e7c-ac33-bd635a7cda83" />

* Pushed inside Docker Hub
  <img width="1907" height="503" alt="hub" src="https://github.com/user-attachments/assets/3a5cd2ad-9dd5-46fa-b137-7f9acb0b3b43" />


## EC2 Instance Creation
Open AWS Console and navigate to AWS EC2 click on launch instance and add name , AMI Image as ubuntu , instance type as t2.medium
<img width="1259" height="691" alt="instance 2" src="https://github.com/user-attachments/assets/2e05d34f-6d2d-4fb1-85d0-9cd039d65de6" />

<img width="1394" height="714" alt="instance 3" src="https://github.com/user-attachments/assets/42a11193-8703-4ba3-86ba-60ccb82e1c7b" />

<img width="1919" height="763" alt="instance launched" src="https://github.com/user-attachments/assets/9992d82e-9192-4281-af57-404669be3694" />


## Now by using EC2 Connect , connect to the server
<img width="1919" height="887" alt="ec2 connect" src="https://github.com/user-attachments/assets/08d78203-a150-4c22-94db-04174fb81cfb" />

## Update and install docker & docker compose
* - sudo apt update
* - sudo install docker.io
*  - sudo install docker-compose
## Now create a Docker-compose file:
* vi docker-compose.yml
write the docker-compose file and give :
* - docker compose up -d
<img width="1919" height="338" alt="docker-compose yml" src="https://github.com/user-attachments/assets/8504723b-cb29-4b15-8195-a17340f50aab" />


* it should pull the frontend,backend and database from the Docker Hub
  <img width="1919" height="673" alt="docker up" src="https://github.com/user-attachments/assets/5dd7747b-638d-4afb-97de-d94239d6d12d" />

## Step 3 : CI/CD Pipeline Configuration
* For CI/CD i have used Github Actions.
*  add new repo .github/workflows/docker.yml
  
  <img width="1871" height="816" alt="github create" src="https://github.com/user-attachments/assets/79e0234c-a827-4124-a6a5-5c89cae0121a" />

* Create repository secrets
  <img width="1902" height="913" alt="secret" src="https://github.com/user-attachments/assets/3efc7eed-4d08-4e9f-add7-a8ffabfdca15" />

* Click on Actions , the pipeline should build
  <img width="1919" height="862" alt="build-git" src="https://github.com/user-attachments/assets/02d7633b-9c1b-4f7f-a30f-e48e70a1e168" />

## Step 4: Nginx Reverse Proxy
* Create nginx.config file
*  vi nginx.conf

 <img width="1916" height="829" alt="image" src="https://github.com/user-attachments/assets/27789b71-a5e7-43d2-8734-4ac83e61e1fc" />


## Application can be accessed from the EC2-public-ip
<img width="1919" height="827" alt="op1" src="https://github.com/user-attachments/assets/aff1004b-b6ef-41ed-bfbc-3f38b5be9f6a" />
<img width="1918" height="743" alt="op2" src="https://github.com/user-attachments/assets/050acafb-26a5-4606-94f0-69376d1728fd" />


  
















