# Basic Steps for Provisioning and Deploying ArgoCD on Kubernetes
1. **Install ArgoCD**

    ```bash
    kubectl create namespace argocd
    kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
    ```
![ArgoCD!](/doc/images/629226.gif "ArgoCD")


2. **Access the ArgoCD UI**

   Once installed, you can access the ArgoCD UI using port-forwarding or by exposing the service externally:

    ```bash
    kubectl port-forward svc/argocd-server -n argocd 8080:443
    ```
![ArgoCD!](/doc/images/629227.gif "ArgoCD")
   Open a browser and visit `https://localhost:8080`. You might need to accept the self-signed certificate to proceed.

3. **Login to ArgoCD**

   Use the default username and password to login:

    ```
    Username: admin
    Password: <retrieve admin password>
    ```

   You can retrieve the admin password using:

    ```bash
    kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d && echo
    ```

![ArgoCD!](/doc/images/629228.gif "ArgoCD")
These steps will get you started with running ArgoCD.


![ArgoCD!](/doc/images/intro.gif "ArgoCD")
