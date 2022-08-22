

        agent any

        environment {
                DOCKERHUB_CREDENTIALS=credentials('shivanisingh987')
        }

        stages {

                stage('Build') {

                        steps {
                                sh 'docker build -t shivanisingh987/docker-push-jenkins:latest .'
                        }
                }

                stage('Login') {

                        steps {
                                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                        }
                }

                stage('Push') {

                        steps {
                                sh 'docker push shivanisingh987/docker-push-jenkins:latest .'
                        }
                }
        }

        post {
                always {
                        sh 'docker logout'
                }
        }

}
