### README - Deployment Steps

**1. Repo Structure**

- `app`: Contains the application received with Docker files and Flask app.
- `helmChart`: Contains the `backend-node-app` and `frontend-node-app` Helm charts.
- `others`: Contains the `Vagrantfile`.
- `README.md`

**2. Download and Configure Virtual Box & Vagrant**

- Vagrant file path: `ordersApp/others/Vagrantfile`
- Commands to initialize and SSH into CentOS 8 VM with Vagrant:

    ```bash
    vagrant init centos/8
    vagrant up
    vagrant ssh
    ```

**3. Install Required Packages**

- Use `yum install` command to install necessary packages like Docker, Git, Python3, Node.js 14, etc.

**4. Create Flask Application on top of the frontend**
- Create a Flask application to run the `index.html` and return the `html_content`.
- Flask application path: `ordersApp/app/frontend/app.py`

**5. Pull MongoDB Image and Run It**

- using: `docker pull mongo`

**6. Export MONGODB_URL**

- Run the following command to export the MongoDB URL to backend:

    ```bash
    export MONGODB_URL="mongodb://0.0.0.0:27017"
    ```

**7. Create Docker Files**

- Dockerfiles path:
  - Frontend: `ordersApp/app/frontend/Dockerfile`
  - Backend: `ordersApp/app/backend/Dockerfile`

**8. Push Docker Files to Docker Hub**

- Docker Hub Repository URL: [Node.js Application](https://hub.docker.com/repository/docker/danielzerihon/nodejs_application/general)

**9. Install k3s and Helm Chart**

**10. Install MongoDB Helm Charts**

- Commands:

    ```bash
    helm repo add bitnami https://charts.bitnami.com/bitnami
    helm install mongodb bitnami/mongodb
    ```

**11. Create Helm Charts for Frontend and Backend separately**

- Deploy two different charts, one for the frontend and the other for the backend.
