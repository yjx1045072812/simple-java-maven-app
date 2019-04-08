pipeline{
	agent{
		label 'windows7'
	}
	stages{
		stage('Build'){
			steps{
				bat 'mvn -B -DskipTests clean package'
			}
		}
		stage('Test'){
			steps{
				bat 'mvn test'
			}
			post {
				always {
					junit 'target/surefire-reports/*.xml'
				}
			}
		}
		stage('Deliver'){
			steps{
				echo './jenkins/scripts/deliver.sh'
			}
		}
	}

}
