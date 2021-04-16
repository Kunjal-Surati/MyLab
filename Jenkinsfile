pipeline {
    //Directives
    agent any
    tools {
        maven 'maven'
    }
    
    stage {
            //1. build stage
            stage ('Build') {
                steps {
                    sh 'maven clean package install'

                }

            }
            // 2.testimg stage
            stage ('test') {
                 steps {
                    echo ' testing..'
                }

            }
            // 3. deploying stage
            stage ('deploy') {
                steps {
                    echo 'deploying'
                }
            }
                        
    }

}