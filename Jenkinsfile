pipeline {
    agent {
    docker {
      image "python:3.8"
    }
  }

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'GitID', url: 'https://github.com/shreemansandeep/python-web-app.git'            }
        }
        stage('Build') {
            steps {
                sh "pip install -r requirements.txt"
                sh "python app.py"
            }
        }
        stage('Test') {
            steps {
                sh 'python3 -m pytest'
            }
        }
    }
}
