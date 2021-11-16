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

	    stage('Build') {
		 steps { 
		  script{ 
		  sh "ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml "
				}
			       }
			}

	}
}
