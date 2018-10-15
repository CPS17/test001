pipeline {
    agent {
        docker {
        image 'container:local'
            args '--expose 3000 --network proxy_nw'
        }
    }
    environment {
        CI = 'true'
        COMMIT_TEXT = sh (
            script: 'git log --format="full" -1 ${GIT_COMMIT}',
            returnStdout: true
        ).trim()

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

//discordSend description: 'J Pipeline Build', footer: "env.COMMIT_TEXT", link: env.BUILD_URL, successful: currentBuild.resultIsBetterOrEqualTo('SUCCESS'), unstable: false, title: JOB_NAME, webhookURL: 'https://discordapp.com/api/webhooks/496992026932543489/4exQIw18D4U_4T0H76bS3Voui4SyD7yCQzLP9IRQHKpwGRJK1-IFnyZLyYzDmcBKFTJw'
echo "t1"
echo env.COMMIT_TEXT
echo env.BUILD_URL             
        }
    }

}
