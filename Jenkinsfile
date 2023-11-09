pipeline {
	agent any 
	parameters {
        choice(name: 'ENVIRONMENT', choices: ['Dev','QA','UAT','Prod'], description: 'Pick Environment value')
	}
	triggers {
        pollSCM '* * * * *'
        }
	 stage('Slave') {
	    steps {
		node('Mens-label') {
    // some block
                   }}			       
	            
	stage('Checkout') {
	    steps {
		checkout scm			       
	          }}
	   stage('Build') {
	     steps {
		  sh '/home/tom/slave-dir/apache-maven-3.9.5/bin/mvn install'
	          }}
	   stage('Deployment'){
	     steps {
		  sh 'cp target/Oneplus.war /home/tom/slave-dir/apache-tomcat-9.0.82/webapps'
		  }}	
          
