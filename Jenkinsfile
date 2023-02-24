pipeline{
		agent any
		stages{
				stage("Pull Latest Image"){
						steps{
							sh "docker pull lautarorial/selenium-docker"
						}
				}
				stage("Run Grid"){
						steps{
							sh "docker-compose up -d hub chrome firefox"
						}
				}
				stage("Run Tests") {
						steps { 
							sh "docker-compose up test-module-one test-module-two"
						}
				}
		}
		post{
			always{
				archiveArtifacts artifacts: 'output/**'
				sh "docker-compose down"
			}
		}
}