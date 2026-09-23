pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Show Build Info') {
            steps {
                echo "=== Jenkins Build Information ==="
                echo "Build Number: ${env.BUILD_NUMBER}"
                echo "Job Name: ${env.JOB_NAME}"
                echo "Workspace Path: ${env.WORKSPACE}"
            }
        }
        stage('Run Linter') {
            steps {
                echo "Installing flake8..."
                bat "python -m pip install flake8"
                echo "Running flake8 linter on app.py..."
                bat "python -m flake8 app.py"
            }
        }
    }
}
