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
                nexusArtifactUploader artifacts: [[artifactId: 'SankarDevOpsLab', classifier: '', file: 'target/SankarDevOpsLab-0.0.5-snapshot.war', type: 'war']], credentialsId: '5c64d256-cc5d-4d2e-86f6-891d35ea4b6c', groupId: 'com.sankardevopslab', nexusUrl: '172.20.10.113', nexusVersion: 'nexus3', protocol: 'http', repository: 'SankarDevOpsLab-Snapshot', version: '0.0.5-snapshot'
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