pipeline {
    agent any

    stages {
        stage('A') {
            steps {
            git branch: 'main', credentialsId: '5b526cd3-b2f2-4778-9f96-3cc78853c79d', url: 'https://github.com/sulimansabha/orange.git'}
        }
    } 
stage('apt update') {
            steps {
                sh 'sudo apt update -y'
    }

}

stage ('docker repo') {
steps {
sh 'sudo apt install apt-transport-https ca-certificates curl software-properties-common'
sh 'curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -'
sh 'sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"'
sh 'sudo apt install docker-ce'
}}
    




   stage('B') {
            steps {
                sh 'docker build -t image-from-jenkins:v1 .'
    }
        }
        stage('C') {
            steps {
                        sh 'echo done image creaeted'

    }
        }
    }


