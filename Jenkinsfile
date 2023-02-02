pipeline{
    agent any
    tools{
        maven 'local_maven'
    }
    stages{
        stage ("Build"){
            steps{
                sh 'mvn clean package'
            }
            post{
                success{
                    echo "Archiving the Artifacts"
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage ('Build Docker Image'){
            steps {
                // Build the Docker image from the artifact
                sh 'docker build -t thursday .'
            }
        }

    }
    
}