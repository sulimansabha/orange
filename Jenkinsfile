pipeline {
    agent any

    stages {
        stage('A') {
            steps {
            git branch: 'main', credentialsId: '5b526cd3-b2f2-4778-9f96-3cc78853c79d', url: 'https://github.com/sulimansabha/orange.git'}
        }
     
stage('apt update') {
            steps {
                sh 'apt update -y'
    }

}




   stage('docker install') {
            steps {
                sh 'apt install docker -y'
    }

}


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
}
