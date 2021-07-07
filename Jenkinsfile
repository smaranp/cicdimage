pipeline {
    agent {
  label 'l-slave1'
}
    stages{
	    stage('Jenkin Env'){
		  steps{
		      sh 'printenv'
		   }
		}
		stage('Build'){
			steps{
				echo "*******Build Application Using Mvn*********"
				sh ''' 
					pwd
					ls -l
					mvn clean package
				'''
				
			}
		}
		stage('Deploy'){
		  steps{
		   deploy adapters: [tomcat9(credentialsId: '6985919a-c19e-49a8-ae07-a20808c74592', path: '', url: 'http://13.213.37.32:8080/')], contextPath: 'test1', war: '**/*.war'
		   }
		}
	}
}
