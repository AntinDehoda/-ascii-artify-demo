# Creating a new application in ArgoCD

![ArgoCD!](/doc/images/argo-app.gif)

Add port forwarding
```bash
k port-forward -n demo svc/ambassador 8088:80
```
Download random png file
```bash
wget -O /tmp/g.png https://upload.wikimedia.org/wikipedia/commons/thumb/e/e3/Columns_of_Gediminas.png/240px-Columns_of_Gediminas.png
```
Upload this file to the converter
```bash
curl -F 'image=@/tmp/g.png' localhost:8088/img/
```

You should observe something like this

![ArgoCD!](/doc/images/ambassador.gif)
