pipeline {
	agent any
	tools {
		maven 'Maven 3.9.9'
		java 'Java JDK 17'
	}
	stages{
		stage("clean") {
			step {
				echo "Start Clean"
				bat "mvn clean"
			}
		}
		Stage("test") {
			steps{
				echo "Start Test"
				bat "mvn test"
			}
		}
		stage("build") {
			steps {
				echo "start build"
				bat "mvn install -DskipTests"
			}
		}
		
	}
}