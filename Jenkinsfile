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
          git branch: 'master', credentialsId: 'Git ton', url: 'https://github.com/CPS17/test001.git'
       }
       stage('stage 01') {
          sh 'echo 01'
        }
    }
}
