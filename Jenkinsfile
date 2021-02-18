pipeline {
    agent any
    tools{
      ant 'ant1.10.9'
    }
    stages {
        stage('Example') {
            steps {
                git(url: 'https://github.com/darealmc/some_java.git', branch: 'master')
            }
        },
        stage('Second Step') {
            steps {
                echo "Second step"
            }
        }
    }
    post { 
        success { 
            slackSend  message:" BUILD_NUMBER = ${BUILD_NUMBER}:\n JOB_NAME= ${JOB_NAME} \n BUILD_NUMBER = ${BUILD_NUMBER}:\n${BUILD_URL}"
        }
        failure{
            slackSend  message: "BUILD_NUMBER = ${BUILD_NUMBER}:\n JOB_NAME = ${JOB_NAME} \n BUILD_NUMBER =${BUILD_NUMBER}:\n${BUILD_URL}"
        }
    }
}