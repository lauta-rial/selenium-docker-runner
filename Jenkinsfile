pipeline{
		agent any
		stages{
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
				stage("Stop Grid") {
						steps {
							sh "docker-compose down"
						}
				}
		}
}