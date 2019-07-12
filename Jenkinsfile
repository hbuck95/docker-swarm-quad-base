pipeline{
        agent any
        stages{
		stage('Invest'){
			steps{
				sh "pwd"
				sh "ls -alrt"
			}
		}
                stage('Build Client and Server'){
                        steps{
                                sh "docker-compose build --no-cache"
                        }
                }
		stage('Push Client and Server'){
                        steps{
                                sh "docker-compose push"
                        }
                }
		stage('Deploy Swarm'){
                        steps{
                                sh "docker stack deploy --compose-file docker-compose.yaml quad-base"
                        }
                }
        }
}


