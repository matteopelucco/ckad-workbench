# ckad-workbench
A simple diary of my CKAD experience. 
This repo contains files, folders, Dockerfile, ...

## HelloWorld
A simple "hello-world" application, deployed just to test the K8S environment. 
Composed by: 
- **hello-world-deployment.yaml**: a simple deployment, 1 single replica, tutum image definition
- **hello-world-service.yaml**: simple service managing the hello-world-deployment
- **hello-world-ingress.yaml**: a simple ingress, exposing / to hello-world-service

Note: since my cluster sometimes seems to be unstable, I use this simple deployments bound to UptimeRobot (free tier) to receive notifications about stability of the system (via mail)

## Jellyfin
Jellyfin is a very powerful media server, open and modern. More infos here: https://jellyfin.org.
Composed by: 
- **jellyfin-deployment.yaml**: a simple deployment, 1 single replica, jellyfin image, 2 hostPath Volumes to mount media and config
- **jellyfin-service.yaml**: simple service managing the jellyfin-deployment
- **jellyfin-ingress.yaml**: a simple ingress, exposing /jellyfin to hello-world-service

### Status
2020.11.05: Ehm.. everything was ok, only a problem with another ingress overmapping the "/" path. Solved leaving only Jellyfin on and disabling the other service. So.. success!
2020.11.04: Few progresses, added a "local" mount path, where kubernetes has read / write access. /config and /cache folders are now mounted into my Ubuntu home dir, whereas media files are mounted into /media path. Added nodePort to see if Jellyfin is accessible and.. it is! But still some issues with ingress / services, Jellyfin is running, media folder and config are seen but no access from the outside. But.. progresses :)
2020.11.03: Still working on that.. ingress works, but Jellyfin.. ehm.. need more time..

