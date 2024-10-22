# Flask Docker Application with Jenkins CI/CD

## Project Overview

This project is a Flask-based web application that utilizes Docker for containerization. The project is configured with a Jenkins pipeline to automate the build, test, and deployment processes. The pipeline follows a Continuous Integration/Continuous Deployment (CI/CD) approach, ensuring that every change made to the repository is tested and deployed efficiently.

## Prerequisites

To set up and run this project, you need the following tools installed:

- **Git**: Version control for managing source code.
- **Docker**: For containerizing the Flask application.
- **Jenkins**: Continuous Integration server to automate the build and deployment.
- **Python**: Version 3.8 or higher (used in the Docker environment).

## Project Structure

```bash
├── Dockerfile               # Dockerfile for building the Flask application image
├── JenkinsFile              # Pipeline script for Jenkins
├── requirements.txt         # Python dependencies for the Flask application
├── app/                     # Directory containing Flask application code
│   └── main.py              # Main file for the Flask app
├── tests/                   # Directory containing test scripts (To be added)
└── README.md                # Project documentation
```

## Jenkins Pipeline

The Jenkins pipeline is designed to automate the process from code retrieval to deployment. Below is a breakdown of each stage in the pipeline:

### 1. **Declarative: Checkout SCM**
   - **Objective**: To clone the GitHub repository.
   - **Actions**: 
     - The pipeline pulls the latest code from the `main` branch of the repository.
     - Uses Git to manage version control, ensuring the correct files are checked out.
   - **Result**: Successfully fetched and checked out the specified branch.

### 2. **Clone Repository**
   - **Objective**: To ensure the repository is cloned successfully and set up for further stages.
   - **Actions**:
     - Re-fetches the code to verify repository integrity.
   - **Result**: Confirmed that the main branch is available and correctly cloned.

### 3. **Build Docker Image**
   - **Objective**: To create a Docker image from the Flask application source code.
   - **Actions**:
     - Uses a `Dockerfile` to build the image.
     - The base image is `python:3.8-slim`.
     - Installs dependencies listed in `requirements.txt`.
     - The final image is tagged as `flask-docker-app`.
   - **Result**: Docker image built successfully.

### 4. **Run Tests**
   - **Objective**: To run tests for the application.
   - **Actions**:
     - Placeholder to execute test scripts (can be replaced with actual test commands).
   - **Result**: Tests stage executed successfully, but no actual tests were defined.

### 5. **Deploy**
   - **Objective**: To deploy the application after a successful build and test phase.
   - **Actions**:
     - Placeholder for deploying the Docker container (can be extended based on deployment requirements).
   - **Result**: Deployment stage executed successfully.

## How to Run Locally

To run this project locally, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Aditya19Joshi01/flask-docker-app.git
   cd flask-docker-app
   ```

2. **Build the Docker image**:
   ```bash
   docker build -t flask-docker-app .
   ```

3. **Run the Docker container**:
   ```bash
   docker run -d -p 5000:5000 flask-docker-app
   ```

4. **Access the Application**:
   - Open a web browser and navigate to `http://localhost:5000`.

## Future Enhancements

- **Test Implementation**: Add meaningful test cases using frameworks like `pytest`.
- **Automated Deployment**: Implement automatic deployment using Docker containers or cloud services.
- **Docker Hub Integration**: Integrate the pipeline with Docker Hub to push the Docker image.

## Troubleshooting

- If you encounter any errors during the Jenkins pipeline execution, make sure:
  - The correct GitHub repository URL is specified.
  - Jenkins has access to Docker (Docker installed and configured properly).
  - All required Python packages are listed in `requirements.txt`.

## License

This project is open-source and free to use under the [MIT License](LICENSE).
