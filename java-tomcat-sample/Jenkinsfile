pipeline {
    agent any
    tools {
        maven 'LocalMaven'
        jdk 'jdk8'
    }
    stages {
        stage('Build Application') {
            steps {
                sh 'mvn -f java-tomcat-sample/pom.xml clean package'
            }
            post {
                success {
                    echo "Archiving Artifact... !"
                    archiveArtifacts artifacts : '**/*.war'
                }
            }
        }
        stage('Create Docker Image for Tomcat'){
            steps {
                sh 'docker build ./java-tomcat-sample -t tomcatDockerImage:${env.BUILD_ID}'
            }
        }
    }
}