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
                    withDockerRegistry(credentialsId: '78623ae5-15b7-445d-84ef-69c19ff1ad8d') {
                        docker.image(customImageTag).push()
                    }
                }
            }
        }
stage('Build to Kubernetes') {
            steps {
                script{
                   
		sh 'minikube kubectl apply -f . --kubeconfig kubeconfig '
			 }
                }
            }
        }




    }
}

