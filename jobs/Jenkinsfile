pipeline {
	agent { label 'maven' }

	environment {
		mavenHome = tool 'maven'
	}

	tools {
		jdk 'jdk'
		maven 'maven'
	}

	stages {

		stage('Build'){
			steps {
				sh "mvn clean install -DskipTests"
			}
		}

		stage('Package'){
			steps {
				sh "mvn clean package -DskipTests"
			}
		}

		stage('Test'){
			steps{
				sh "mvn test"
			}
		}

		stage('Deploy') {
			steps {
			    /*sh "mvn jar:jar deploy:deploy"*/
			        sh "echo hello"
			}
		}
	}
	post {
                always {
                         archiveArtifacts artifacts: '**/*.jar', onlyIfSuccessful: true
        }
    }
}
