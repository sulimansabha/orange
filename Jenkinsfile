pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // make git clone
git branch: 'main', credentialsId: '5b526cd3-b2f2-4778-9f96-3cc78853c79d', url: 'https://github.com/sulimansabha/orange.git'            
}
        }
        stage('Build Docker Image') {
            steps {
                script{
                    def customImageTag = "sulimansabha/orange-httpd:sss"
                    docker.build(customImageTag,'.')
                }
            }
        }
        stage('Push docker image') {
            steps {
                script{
                    def customImageTag = "sulimansabha/orange-httpd:sss"
                    withDockerRegistry(credentialsId: 'dckr_pat_mtiMjXfqN4DeWhtYuDMQGaS4ZSU') {
                        docker.image(customImageTag).push()
                    }
                }
            }
        }
    }
}

