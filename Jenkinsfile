pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
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

        //Stage3 : Publish the artifacts to Nexus
        stage('Publish to Nexus') {
            steps{
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.8.war', type: 'war']], credentialsId: '23fa0394-8cd6-4979-b109-5abfbe70cb19', groupId: 'com.vinaysdevopslab', nexusUrl: '10.0.0.164:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'vboDevopsLab-SNAPSHOT', version: '0.0.8'
            }
        }
        // Stage3 : Publish the source code to Sonarqube
       // stage ('Sonarqube Analysis'){
          //  steps {
            //    echo ' Source code published to Sonarqube for SCA......'
                //withSonarQubeEnv('sonarqube'){ // You can override the credential to be used
                  //   sh 'mvn sonar:sonar'
                }

            }
  //      }

        
        
 //   }

//}
