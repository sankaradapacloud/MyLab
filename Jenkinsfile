pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

   // environment{
    //   ArtifactId = readMavenPom().getArtifactId()
    //   Version = readMavenPom().getVersion()
    //   Name = readMavenPom().getName()
   //    GroupId = readMavenPom().getGroupId()
   // }
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
   
       /* stage ('Publish the artifacts to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'mylab', classifier: '', file: 'target/mylab-0.0.1.war', type: 'war']], credentialsId: '340fbd9d-f1bf-4f64-8a59-3bf4b8e24176', groupId: 'com.sankardevopslab', nexusUrl: '172.20.10.119:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'mySample-snapshot', version: '0.0.1'
            }
            
        }*/
        
        // Stage3 : Testing
        stage ('Deploy'){
            steps {
                echo ' deploying......'

            }
        }
        
        
    }
}
