//This is the pipeline code for addressbook deployment 

pipeline{

	tools{
	
		maven 'mymaven'
	}

	agent any
	
	stages{
	
		stage('1.clone the repo') {
		
			steps{
			
			git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
			
			}
		
		}
	
		stage('2.build the code') {
		
			steps{
			
			sh 'mvn compile'
				
			}
		
		}
	
	
		stage('3.review the code') {
		
			steps{
			
			sh 'mvn pmd:pmd'
			
			}
		
		}
	
		stage('4.test the code') {
		
			steps{
			
			sh 'mvn test'
			
			}
		
			post{
			
				success{
				
				junit 'target/surefire-reports/*.xml'
				
				}
			}
			
		}
	
		stage('5.package the code'){
		
			steps{
			
			sh 'mvn package'
			
			}
		
		}
		
	
	}
	

}
