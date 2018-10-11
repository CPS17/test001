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
        stage('Git') {
            steps{
                git branch: 'test01', credentialsId: 'Git ton', url: 'https://github.com/CPS17/test001.git'
            }
        }
        stage('stage 01') {
            steps{
                sh 'echo 01'
            }
        }
        stage('wait'){
            steps{
//            input message: 'Finished using the web site? (Click "Proceed" to continue)'
              echo "echo 02"
            }
        }
    }
}
