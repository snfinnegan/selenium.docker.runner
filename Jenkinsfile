pipeline{
    agent any
    stages{
        stage("start grid"){
            steps {
                bat "docker-compose up -d hub chrome firefox"
            }
        }
        stage("execute flight test suite"){
            steps {
                bat "docker-compose up flight-module1 flight-module2"
            }
        }
    }
    post{
        archiveArtifacts artifacts: 'output/**'
        bat "docker-compose down"
    }
}
