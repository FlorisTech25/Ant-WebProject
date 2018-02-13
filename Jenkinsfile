//Declarative way
pipeline {
    agent any

    stages {
        stage('build') {
            steps {
		echo "My Branch Name: ${env.BRANCH_NAME}"
                sh 'ant'
	    }
	}
    }
	
	post {
        success {
          emailext(
	   subject: "${env.JOB_NAME} [${env.BUILD_NUMBER}] Successfull",
           body: "${env.JOB_NAME} [${env.BUILD_NUMBER}] ${env.BUILD_URL}",
		  to: "${env.DEFAULT_RECIPIENTS},atreya.atreyasa@gmail.com"
          )
        }
	failure{
	   emailext(
	   subject: "${env.JOB_NAME} [${env.BUILD_NUMBER}] Successfull",
           body: "${env.JOB_NAME} [${env.BUILD_NUMBER}] ${env.BUILD_URL}",
		   to: "${env.DEFAULT_RECIPIENTS},atreya.atreyasa@gmail.com"
            )		   
		}
      }
	
}
