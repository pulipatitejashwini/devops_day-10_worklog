# TASK 10: Docker Volumes & Networking – Commands

This document contains all Docker commands used to demonstrate volumes, networking, and data persistence.                   

## 1. Create Docker Volume
`docker volume create app-data`                    
### Verify volume:
`docker volume ls`                    

## 2. Run Container with Volume Attached
`docker run -d --name nginx-volume-container -p 8081:80 -v app-data:/usr/share/nginx/html nginx:alpine`                     

## 3. Store Data Inside the Volume
`docker exec -it nginx-volume-container sh`                
### Inside container:
`echo "Hello from Docker Volume" > /usr/share/nginx/html/index.html`                   
`exit`             

## 4. Verify Data via Browser
Open: `"http://localhost:8081"`                  

## 5. Stop and Remove Container
`docker stop nginx-volume-container`                    
`docker rm nginx-volume-container`                  

## 6. Recreate Container with Same Volume
`docker run -d --name nginx-volume-container-new -p 8081:80 -v app-data:/usr/share/nginx/html nginx:alpine`                   
Verify persistence via browser.              

## 7. Inspect Docker Volume
`docker volume inspect app-data`             

## 8. Create Custom Docker Network
`docker network create app-network`              
### Verify:
`docker network ls`               

## 9. Run Containers in Custom Network
Web Container
`docker run -d --name web-container --network app-network nginx:alpine`                    
Test Container
`docker run -it --name test-container --network app-network busybox sh`                     

## 10. Test Container-to-Container Communication
Inside test-container:                
`ping web-container`               
`exit`               

## 11. Inspect Docker Network
`docker network inspect app-network`                

## 12. Cleanup Resources
`docker stop web-container nginx-volume-container-new`                 
`docker rm web-container nginx-volume-container-new`                                       
`docker volume rm app-data`                 
`docker network rm app-network`                
