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
        stage('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'SankarDevOpsLab', classifier: '', file: 'target/SankarDevOpsLab-0.0.5-snapshot.war', type: 'war']], credentialsId: '9a6c1591-11a8-405c-b947-f5d5cc6530fb', groupId: 'com.sankardevopslab', nexusUrl: '172.20.10.53:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'SankarDevOpsLab-Snapshot', version: '0.0.5-snapshot'
            }
        }
        // Stage4 : Deploying
        stage ('Deploy'){
            steps {
                echo ' deploying......'

            }
        }

        
        
    }

}