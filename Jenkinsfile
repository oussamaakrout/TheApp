pipeline
{
	agent any
	 stages {
	   stage('pull') {
		steps{
		  script{
		     checkout([$class: 'GitSCM', branches: [[name: '*/master']],
			userRemoteConfigs: [[
					credentialsId: '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',				
				url: 'https://github.com/oussamaakrout/TheApp.git']]])
		
			}
			}
			}
          stage('docker') {
               steps{
                  script{
                    sh "ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml "
                }
            }
        }


	}
}
