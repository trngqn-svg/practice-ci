pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                // Checkout code
                checkout scm

                // Setup Python + install dependencies
                sh '''
                    python3 -m pip install --upgrade pip
                    pip3 install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                // Cài lại dependency (giống GitHub Actions)
                sh '''
                    python3 -m pip install --upgrade pip
                    pip3 install -r requirements.txt
                '''

                // Run pytest
                sh 'pytest --ignore=Answer'
            }
        }
    }
}
