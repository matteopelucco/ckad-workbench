# ckad-workbench
A simple diary of my CKAD experience. 

This repo contains files, folders, Dockerfile, ...

## HelloWorld
A simple "hello-world" application, deployed just to test the K8S environment. 
Composed by: 
- hello-world-deployment.yaml: a simple deployment, 1 single replica, tutum image definition
- hello-world-service.yaml: simple service managing the hello-world-deployment
- hello-world-ingress.yaml: a simple ingress, exposing / to hello-world-service

Note: since my cluster sometimes seems to be unstable, I use this simple deployments bound to UptimeRobot (free tier) to receive notifications about stability of the system (via mail)

## Jellyfin
Jellyfin is a very powerful media server, open and modern. More infos here: https://jellyfin.org
Composed by: 
- jellyfin-deployment.yaml: a simple deployment, 1 single replica, jellyfin image, 2 hostPath Volumes to mount media and config
- jellyfin-service.yaml: simple service managing the jellyfin-deployment
- jellyfin-ingress.yaml: a simple ingress, exposing /jellyfin to hello-world-service

### status
Still working on that.. ingress works, but Jellyfin.. ehm.. need more time..

