# Argo CD Flask Deployment

This project contains a simple Flask application that is deployed to a Kubernetes cluster using Argo CD. The Flask application provides two endpoints, the root endpoint that returns "Hello World! Deployed using Argo CD!" and the '/around' endpoint that returns "Isn't Argo CD pretty amazing?".

## Table of Contents

- [Project Structure](#project-structure)
- [Local Setup](#local-setup)
- [Deploying with Argo CD](#deploying-with-argo-cd)
- [Contributing](#contributing)
- [License](#license)

## Project Structure

- `Dockerfile`: Builds a Docker image of the Flask application.
- `main.py`: The Flask application source code.
- `requirements.txt`: Lists the Python dependencies.
- `deployment.yaml`: Configures the Kubernetes deployment.
- `service.yaml`: Configures the Kubernetes service.

## Local Setup

To build and run the application locally:

1. **Build the Docker image**
   ```bash
   docker build -t hello-app .
2. **Run the Docker containe**
   ```bash
   docker run -p 5000:5000 hello-app
You can now access the Flask application at http://localhost:5000.

## Deploying with Argo CD

To deploy this application to a Kubernetes cluster using Argo CD, follow the detailed steps provided below:

### Install Argo CD on your Kubernetes cluster

If you haven't installed Argo CD on your cluster yet, refer to the official Argo CD [Getting Started](https://argo-cd.readthedocs.io/en/stable/getting_started/) guide.

### Connect your Git repository to Argo CD

To connect your Git repository to Argo CD:

1. Open the Argo CD UI in your browser.
2. Click on `New App` to create a new application.
3. In the `Application Details` section, enter your chosen application name and select your project.
4. In the `Source` section, enter the URL of your Git repository.
5. In the `Destination` section, select the cluster and namespace where you want your application to be deployed.
6. Click `Create` to finish connecting your repository to Argo CD.

### Sync your Application in Argo CD

After you have connected your repository:

1. Navigate to your application on the Argo CD UI.
2. Click `Sync` to initiate the synchronization process.
3. Confirm the synchronization to let Argo CD deploy your application according to the configurations in your `deployment.yaml` and `service.yaml` files.

### Access the Application

Once your application is synced and running, you can access it as follows:

1. In your Kubernetes dashboard, navigate to `Services`.
2. Find and click on your service (named 'hello-app-service' in `service.yaml`).
3. Under `External endpoints`, you'll find the IP and port to access your service.
4. Open a browser and navigate to the provided service endpoint to view and interact with your Flask application.

## Contributing

We welcome contributions to this project! To contribute:

- Fork this repository
- Create a new branch with your feature (`git checkout -b feature/AmazingFeature`)
- Commit your changes (`git commit -m 'Add some AmazingFeature'`)
- Push to the branch (`git push origin feature/AmazingFeature`)
- Open a Pull Request

## License

This project is licensed under the MIT License - see the [MIT License](https://choosealicense.com/licenses/mit/) page for details.
