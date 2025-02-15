pipeline {
    agent any
    tools {
        maven 'Maven 3.9.9'
        jdk 'Java JDK 17'
    }
    stages {
        stage("clean") {
            steps {
                echo "Start Clean"
                bat "mvn clean"
            }
        }
        stage("test") {
            steps {
                echo "Start Test"
                bat "mvn test"
            }
        }
        stage("build") {
            steps {
                echo "Start Build"
                bat "mvn install -DskipTests"
            }
        }
        stage("sonar") {
            environment {
                scannerHome = tool 'SonarQube Scanner'
            }
            steps {
                withSonarQubeEnv('SonarQube') {
                    bat "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
    post {
        always {
            echo "Pipeline completed"
        }
    }
}
