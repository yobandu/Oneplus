pipeline {
   agent any
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
