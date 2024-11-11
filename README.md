# wp-mysql-kustomize

# WordPress MySQL Kubernetes Deployment

This repository contains a Kubernetes-based setup to deploy a **WordPress** website along with a **MySQL** database using Kubernetes resources. The project leverages `kustomization.yaml` for efficient configuration management, allowing for easy deployment and scaling in Kubernetes clusters.

## 📋 Project Overview

This project demonstrates how to deploy a WordPress website with a persistent MySQL backend in a Kubernetes environment. The setup includes:

- **MySQL Deployment**: Deploys MySQL as a database service with persistent storage.
- **WordPress Deployment**: Deploys a WordPress instance that connects to the MySQL service.
- **Kustomize**: Used for managing Kubernetes configurations, secrets, and deployments.

## 🚀 Features

- **Persistent Storage**: Both MySQL and WordPress data are stored using PersistentVolumeClaims (PVCs) to ensure data is retained even after pod restarts.
- **Secure Configuration**: Uses Kubernetes secrets to securely store the MySQL root password.
- **Scalability**: The deployment is designed to be easily scalable within a Kubernetes cluster.

## 📁 Repository Structure

```
├── kustomization.yaml          # Kustomize configuration file
├── mysql-deployment.yaml       # MySQL service, PVC, and deployment configuration
└── wordpress-deployment.yaml   # WordPress service, PVC, and deployment configuration
```

## 🛠️ Prerequisites

- Kubernetes cluster (e.g., Minikube, GKE, EKS)
- kubectl installed
- kustomize (optional, but recommended)

## ⚙️ Setup and Deployment

1. Clone the repository:
   ```bash
   git clone https://github.com/vaibhav208/wp-mysql-kustomize.git
   cd your-repo-name
   ```

2. Apply the Kubernetes resources using Kustomize:
   ```bash
   kubectl apply -k .
   ```

3. Check the status of the deployments:
   ```bash
   kubectl get pods
   kubectl get services
   ```

4. Access WordPress:
   - Use the `NodePort` assigned to the WordPress service to access it via your browser.
   - Example: `http://<your-node-ip>:<node-port>`

## 📝 Configuration Details

- The MySQL root password is stored securely using a Kubernetes secret (`mysql-pass`).
- WordPress connects to MySQL using the environment variables defined in the `wordpress-deployment.yaml` file.

## 📄 License

This project is licensed under the MIT License.

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

