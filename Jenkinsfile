pipeline {
	agent any 
	parameters {
        choice(name: 'ENVIRONMENT', choices: ['Dev','QA','UAT','Prod'], description: 'Pick Environment value')
	}
	triggers {
        pollSCM '* * * * *'
        }
	mail bcc: '', body: 'Project build is failed please check the same', cc: '', from: '', replyTo: '', subject: 'Build failure', to: 'abhishek.pise80@gmail.com'
        stages {
	  stage('Checkout') {
	    steps {
		checkout scm			       
	          }}
	   stage('Build') {
	     steps {
		  sh '/home/abhishek/apache-maven-3.9.5-bin/apache-maven-3.9.5/bin/mvn install'
	          }}
	   stage('Deployment'){
	     steps {
		  sh 'cp target/Oneplus.war /home/abhishek/apache-tomcat-9.0.82/webapps'
		  }}	
          }}
