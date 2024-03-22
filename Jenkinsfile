pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm // Checks out the source code from the configured SCM
            }
        }


        stage('Run') {
            steps {
                echo 'Starting Flask application...'
                // sh 'nohup python3 app.py > app.log 2>&1 &'
                sh 'sudo docker run -d -p 80:80 httpd'
            }
        }
    }

    post {
        always {
            echo 'Pipeline has finished executing.'
        }
    }
}
