# Node Minikube App

This project is a Node.js application designed to be deployed on a local Minikube cluster using GitHub Actions for continuous integration and deployment.

## Project Structure

```
node-minikube-app
├── server.js               # Main application file
├── k8s
│   └── k8s-node-app.yaml   # Kubernetes configuration for deployment
├── .github
│   └── workflows
│       └── deploy-to-minikube-github-actions.yaml  # GitHub Actions workflow for CI/CD
├── Dockerfile               # Dockerfile for building the application image
├── package.json             # npm configuration file
└── README.md                # Project documentation
```

## Getting Started

### Prerequisites

- Node.js and npm installed on your machine.
- Minikube installed and running.
- Docker installed and configured to work with Minikube.

### Installation

1. Clone the repository:

   ```
   git clone https://github.com/Cezeri73/EpamCD.git
   cd EpamCD/node-minikube-app
   ```

2. Install dependencies:

   ```
   npm install
   ```

### Running the Application Locally

To run the application locally, use the following command:

```
node server.js
```

The application will be accessible at `http://localhost:3000`, and it will respond with "Hello World" when accessed at the root URL.

### Building the Docker Image

To build the Docker image, run the following command:

```
docker build -t node-minikube-app .
```

### Deploying to Minikube

1. Start Minikube:

   ```
   minikube start
   ```

2. Apply the Kubernetes configuration:

   ```
   kubectl apply -f k8s/k8s-node-app.yaml
   ```

3. Access the application:

   ```
   minikube service nodejs-app --url
   ```

### GitHub Actions

This project includes a GitHub Actions workflow that automatically builds the Docker image and deploys the application to Minikube whenever there is a push to the repository. Ensure that your GitHub repository is connected to your Minikube cluster for this to work.

## Author

Murat Kaynar

## License

This project is licensed under the MIT License.