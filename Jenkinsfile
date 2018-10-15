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
                echo env.CHANGE_ID

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
      post { 
        always { 
//discordSend description: 'J Pipeline Build', footer: 'Footer Text', link: env.BUILD_URL, successful: currentBuild.resultIsBetterOrEqualTo('SUCCESS'), unstable: false, title: JOB_NAME, webhookURL: 'https://discordapp.com/api/webhooks/496992026932543489/4exQIw18D4U_4T0H76bS3Voui4SyD7yCQzLP9IRQHKpwGRJK1-IFnyZLyYzDmcBKFTJw'
                echo "Git commit" ::  env.GIT_COMMIT
                sh 'git log --format="medium" -1 ${GIT_COMMIT}'
                
        }
    }

}
