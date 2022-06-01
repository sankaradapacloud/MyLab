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
   
        stage ('Publish the artifacts to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'mylab', classifier: '', file: 'target/mylab-0.1.1-SNAPSHOT.war', type: 'war']], credentialsId: '512e6e02-2da7-4767-945b-6eff3ae086c7', groupId: 'com.sankardevopslab', nexusUrl: '172.20.10.10', nexusVersion: 'nexus3', protocol: 'http', repository: 'Sankaradapa-SNAPSHOT', version: '0.1.1-SNAPSHOT'
                //nexusArtifactUploader artifacts: [[artifactId: 'mylab', classifier: '', file: 'target/mylab-0.1.1-SNAPSHOT.war', type: 'war']], credentialsId: 'd72ed1b0-e5fd-4f05-b8e0-5bd6c234f0fe', groupId: 'com.sankardevopslab', nexusUrl: '172.20.10.187:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'sankar-SNAPSHOT', version: '0.1.1-SNAPSHOT'
                //nexusArtifactUploader artifacts: [[artifactId: 'mylab', classifier: '', file: 'target/mylab.war', type: 'war']], credentialsId: 'd72ed1b0-e5fd-4f05-b8e0-5bd6c234f0fe', groupId: 'com.sankardevopslab', nexusUrl: '172.20.10.187:8081', nexusVersion: 'nexus2', protocol: 'http', repository: 'sankar-SNAPSHOT', version: '0.1.0-SNAPSHOT'
                //nexusArtifactUploader artifacts: [[artifactId: 'mylab', classifier: '', file: 'target/mylab.war', type: 'war']], credentialsId: 'd72ed1b0-e5fd-4f05-b8e0-5bd6c234f0fe', groupId: 'com.sankardevopslab', nexusUrl: '172.20.10.187:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'sankar-SNAPSHOT', version: '0.1.0-SNAPSHOT'
                //nexusArtifactUploader artifacts: [[artifactId: 'mylab', classifier: '', file: 'target/mylab.war', type: 'war']], credentialsId: '4e8fde3b-05cf-42a2-8786-91ad79f3bb98', groupId: 'com.sankardevopslab', nexusUrl: '172.20.10.187:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'sankar-SNAPSHOT', version: '0.1.0-SNAPSHOT'
                //nexusArtifactUploader artifacts: [[artifactId: 'mylab', classifier: '', file: 'target/mylab.war', type: 'war']], credentialsId: '340fbd9d-f1bf-4f64-8a59-3bf4b8e24176', groupId: 'com.sankardevopslab', nexusUrl: '172.20.10.119:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'mySample-snapshot', version: '0.1.0-SNAPSHOT'
                //nexusArtifactUploader artifacts: [[artifactId: 'mylab', classifier: '', file: 'target/mylab.war', type: 'war']], credentialsId: '340fbd9d-f1bf-4f64-8a59-3bf4b8e24176', groupId: 'com.sankardevopslab', nexusUrl: '172.20.10.119:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'mySample-snapshot', version: '0.0.1'
            }
            
        }
        
        // Stage3 : Testing
        stage ('Deploy'){
            steps {
                echo ' deploying......'

            }
        }
        
        
    }
}
