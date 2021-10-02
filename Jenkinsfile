pipeline {
    agent any
    stages {
        stage('compile') {
	   steps {
                echo 'compiling..'
		git url: 'https://github.com/lerndevops/DevOpsClassCodes'
		sh script: 'mvn compile'
           }
        }
        stage('unit-test') {
	   steps {
                echo 'unittest..'
	        sh script: 'mvn test'
                 }
	   post {
               success {
                   junit 'target/surefire-reports/*.xml'
               }
           }			
        }
        stage('package') {
	   steps {
                echo 'package......'
		sh script: 'mvn package'	
           }		
        }
    }
}
