# devops_day-10_worklog
# TASK 10: Docker Volumes & Networking

## Overview
This task demonstrates Docker volumes for data persistence and Docker networking for container-to-container communication.               

## Objectives
- Understand container data loss problem              
- Use Docker volumes for persistent storage      
- Create and use custom Docker networks         
- Verify data persistence after container removal              
- Test container-to-container communication           

## Tools & Technologies
- Docker         
- Nginx             
- BusyBox            
- Linux             

## Problem Statement
Containers are ephemeral in nature. When a container is deleted, all data stored inside it is lost.             
Docker volumes solve this problem by storing data outside the container lifecycle.            

## Docker Volumes
- Volumes store persistent data             
- Volumes survive container deletion              
- Volumes can be reused by multiple containers               
### Volume Used
- `app-data`        

## Docker Networking
- Custom Docker networks enable isolated communication               
- Containers communicate using container names (DNS-based)              
- No need for IP addresses           
### Network Used
- `app-network`          
  
## Data Persistence Verification
1. Data written inside container using volume                  
2. Container deleted             
3. New container created using same volume            
4. Data remained intact         
   
✔ Data persistence successfully verified            

## Container Communication Test
- Two containers connected to the same network           
- Ping tested using container name             
- Communication successful            

## Outcome
This task provided hands-on understanding of Docker volumes, networking, data persistence, and container communication.              

