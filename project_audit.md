=== CURRENT PROJECT AUDIT ===
Date: Tue Jul 29 04:09:24 EAT 2025

## Existing Roles:
total 20
drwxrwxr-x 5 jeremy jeremy 4096 Jul 29 04:08 .
drwxrwxr-x 7 jeremy jeremy 4096 Jul 29 04:09 ..
drwxrwxr-x 4 jeremy jeremy 4096 Jul 29 04:08 backend-deployment
drwxrwxr-x 4 jeremy jeremy 4096 Jul 29 04:08 frontend-deployment
drwxrwxr-x 4 jeremy jeremy 4096 Jul 29 04:08 setup-mongodb
## Docker Configuration:
✅ docker-compose.yaml exists
#This file builds the Docker images for a React/NodeJS application and runs it as microservices on Docker containers

#To ensure successful execution, clone this entire repository and execute this file while in the root folder of the cloned repository

#It's also a requirement to have Docker and the docker-compose plugin installed in your environment

#To launch this app without having to clone the entire repository,use the docker-compose.yaml file to run the app

version: "3.8"

## Ansible Configuration:
✅ playbook.yml exists
---
- name: Ansible playbook to dockerize and run yolo e-commerce app using ansible
  hosts: all
  become: true
  roles: 
    - frontend-deployment
    - setup-mongodb   
    - backend-deployment
    ## Application Structure:
Backend files:
total 88
drwxrwxr-x 4 jeremy jeremy  4096 Jul 29 04:08 .
drwxrwxr-x 7 jeremy jeremy  4096 Jul 29 04:09 ..
-rw-rw-r-- 1 jeremy jeremy   336 Jul 29 04:08 .gitignore
-rw-rw-r-- 1 jeremy jeremy   596 Jul 29 04:08 Dockerfile
drwxrwxr-x 2 jeremy jeremy  4096 Jul 29 04:08 models
-rw-rw-r-- 1 jeremy jeremy 51383 Jul 29 04:08 package-lock.json
-rw-rw-r-- 1 jeremy jeremy   814 Jul 29 04:08 package.json
drwxrwxr-x 3 jeremy jeremy  4096 Jul 29 04:08 routes
-rw-rw-r-- 1 jeremy jeremy  1064 Jul 29 04:08 server.js
-rw-rw-r-- 1 jeremy jeremy   867 Jul 29 04:08 upload.js
Frontend files:
total 840
drwxrwxr-x 4 jeremy jeremy   4096 Jul 29 04:08 .
drwxrwxr-x 7 jeremy jeremy   4096 Jul 29 04:09 ..
-rw-rw-r-- 1 jeremy jeremy    336 Jul 29 04:08 .gitignore
-rw-rw-r-- 1 jeremy jeremy    561 Jul 29 04:08 Dockerfile
-rw-rw-r-- 1 jeremy jeremy   2891 Jul 29 04:08 README.md
-rw-rw-r-- 1 jeremy jeremy 825664 Jul 29 04:08 package-lock.json
-rw-rw-r-- 1 jeremy jeremy    867 Jul 29 04:08 package.json
drwxrwxr-x 2 jeremy jeremy   4096 Jul 29 04:08 public
drwxrwxr-x 4 jeremy jeremy   4096 Jul 29 04:08 src
