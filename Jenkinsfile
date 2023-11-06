pipeline {
	agent any 
	parameters {
        choice(name: 'ENVIRONMENT', choices: ['Dev','QA','UAT','Prod'], description: 'Pick Environment value')
	}
	triggers {
        pollSCM '* * * * *'
        }
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
          
post {
        failure {
            script {
                emailext(
                    subject: "Build Failed: ${currentBuild.fullDisplayName}",
                    body: """
                    The build has failed.

                    Build Details:
                    - Project: ${JOB_NAME}
                    - Build Number: ${BUILD_NUMBER}
                    - Build URL: ${BUILD_URL}
                    - Changes: ${CHANGES, showPaths: false, format: "  %a: %r %p %m"}
                    """)
	           }
	        }
     }  
           }
