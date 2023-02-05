pipeline{
    agent none
    stages{
        stage("static code analysis"){
            agent {
                docker {
                    image: 'maven'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-qube-token') {
                            sh "mvn sonar:sonar"
                    }
                }
            }
        }
    }
}