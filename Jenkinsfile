pipeline{
	agent any
	tools{
	jdk 'Java17'
	maven 'Maven3'
	}
	
	triggers{
		pollSCM('H/2 * * * *')
	}

		stages{
			stage('clean')
				steps{
					cleanWs()
					
				}
			stage("checkout scm")
                         	 steps{
                                        git branch: 'master', credentialsId 'github', url: https://github.com/ashrithasgit/pip.git

                                }
			stage("build")
                                 steps{
                                        sh "mvn clean package"
 
                                }
			stage("test")
                                 steps{
                                        sh "mvn test"
 
                                }



		


		}

}
