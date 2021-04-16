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

        // Stage3 : Publish the source code to Sonarqube
        stage ('Deployment'){
            steps {
                echo 'deployment done'
                
                }

            }
        }

        
        
    }

