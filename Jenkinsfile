pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                  sh 'docker container prune -f'
                checkout scm // Checks out the source code from the configured SCM
            }
        }


        stage('Run') {
            steps {
                echo 'Starting Flask application...'
                // sh 'nohup python3 app.py > app.log 2>&1 &'
                sh 'docker-compose up -d'
            }
        }
    }

    post {
        always {
            echo 'Pipeline has finished executing.'
        }
    }
}
