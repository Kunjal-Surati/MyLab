pipeline{
    //Directives
    agent any
    tools {
        maven 'Maven' //as givin in jenkins console
    }

    environment {
        ArtifactId = readMavenPom().getArtifactId()
        Version = readMavenPom().getVersion()
        GroupId = readMavenPom().getGroupId()
        Name = readMavenPom().getName()

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
                script{

                def NexusRepo =  Version.endsWith("SNAPSHOT") ? "MyLab-SNAPSHOTS" : "MyLab-RELEASE"

                nexusArtifactUploader artifacts:
                [[artifactId: "${ArtifactId}",
                classifier: '', 
                file: 'target/KunjalDevOpsLab-0.0.4.war', 
                type: 'war']], 
                credentialsId: 'a68daa0a-639e-4ff3-8ce9-4936ed9d8a58', 
                groupId: "${GroupId}", 
                nexusUrl: '172.20.10.110:8081', 
                nexusVersion: 'nexus3', 
                protocol: 'http', 
                repository: "${NexusRepo}", 
                version: "${Version}"
                }
            }
        }

        // stage 4: display maven variable
        stage ('print environment variable'){
            steps{
                echo " ArtifactId is '${ArtifactId}'"
                echo "Version is '${Version}'"
                echo "Groupid is '${GroupId}'"
                echo "Name is '${Name}'"
            }
        }

        // Stage5 : Publish the source code to Sonarqube
        stage ('Deployment'){
            steps {
                echo 'deployment done'
                
                }

            }
        }

        
        
    }

