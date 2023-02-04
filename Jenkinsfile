pipeline{
    agent any
    tools{
        maven 'local_maven'
    }
    stages{
        stage ("Build Maven"){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/ttikare/hello-world.git']]])
                sh 'mvn clean install'
            }
        }
    }
}

                