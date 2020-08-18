pipeline {
    agent any
    stages {
        stage('Build') {
            tools {
                jdk 'jdk8'
                maven 'apache-maven-3.6.1'
            }
            steps {
                echo "Build Project"
                powershell label: '', script: 'mvn clean package -f spring-boot-samples\\spring-boot-sample-atmosphere\\pom.xml'
            }
        }
    }
    post {
        always {
                archiveArtifacts artifacts: 'spring-boot-samples/spring-boot-sample-atmosphere/target/*.jar', followSymlinks: false
        }
    }
}
