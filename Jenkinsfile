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
//                sh 'wget  https://sh.rustup.rs -O rust.sh'
//                sh 'chmod 770 rust.sh'
//                sh 'rust.sh -y'
//                sh 'rm rust.sh'
                sh 'curl https://sh.rustup.rs -sSf | sh'
                sh 'export PATH="${HOME}/.cargo/bin:${PATH}"'
            }
        }
    }
}
