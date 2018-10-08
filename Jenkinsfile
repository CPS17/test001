pipeline {
    agent {
        docker {
            image 'container:local'
            args '--expose 3000 --network proxy_nw'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('stage 01') {
            steps {
                sh 'echo 01'
            }
        }
    }
}
