pipeline {
	agent{
	label 'Mens-label'
	}
	stages {
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
}}
