pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    environment{
       ArtifactId = readMavenPom().getArtifactId()
       Version = readMavenPom().getVersion()
       Name = readMavenPom().getName()
       GroupId = readMavenPom().getGroupId()
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
                nexusArtifactUploader artifacts: [[artifactId: 'SankarDevOpsLab', classifier: '', file: 'target/SankarDevOpsLab-0.0.7-SNAPSHOT.war', type: 'war']], credentialsId: 'd0d71460-cc7f-4aba-adba-0d037cc47592', groupId: 'com.sankardevopslab', nexusUrl: '172.20.10.82:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'SankarDevOpsLab-SNAPSHOT', version: '0.0.7-SNAPSHOT'
                script {

                    def NexusRepo = Version.endsWith("SNAPSHOT") ? "SankarDevOpsLab-SNAPSHOT" : "SankarDevOpsLab-RELEASE"
                    nexusArtifactUploader artifacts: 
                    [[artifactId: "${ArtifactId}",
                    classifier: '', 
                    file: "target/${ArtifactId}-${Version}.war",
                    type: 'war']], 
                    credentialsId: 'd0d71460-cc7f-4aba-adba-0d037cc47592', 
                    groupId: "${GroupId}", 
                    nexusUrl: '172.20.10.82:8081', 
                    nexusVersion: 'nexus3', 
                    protocol: 'http', 
                    repository: "${NexusRepo}", 
                    version: "${Version}"
                }
            }
        }

        //Stage 4 : Print some information
        stage ('Print Environment variables'){
            steps {
                echo "Artifact ID is '${ArtifactId}'"
                echo "Version is '${Version}'"
                echo "GroupID is '${GroupId}'"
                echo "Name is '${Name}'"

            }
        }

        // Stage5 : Deploying
        stage ('Deploy'){
            steps {
                echo ' deploying......'

            }
        }

        
        
    }

}