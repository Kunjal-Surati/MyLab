pipeline{
    //Directives
    agent any
    tools {
        maven 'Maven' //as givin in jenkins console
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

        // stage 3: upload to nexus
        stage ('publish to Nexus'){
            steps{
                nexusArtifactUploader artifacts: [[artifactId: 'KunjalDevOpsLab', classifier: '', file: 'target/KunjalDevOpsLab-0.0.3-SNAPSHOT', type: 'war']], credentialsId: 'a68daa0a-639e-4ff3-8ce9-4936ed9d8a58', groupId: 'com.kunjaldevopslab', nexusUrl: '54.92.159.150:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'MyLab-SNAPSHOTS', version: '0.0.3-SNAPSHOT'
            }
        }

        // Stage4 : Publish the source code to Sonarqube
        stage ('Deployment'){
            steps {
                echo 'deployment done'
                
                }

            }
        }

        
        
    }

