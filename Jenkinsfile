

pipeline {
    agent { 
		docker {
			image 'maven:3.5-alpine' 
			label 'jenkins-node2'
		}
	}
    stages {
        stage ('Checkout') {
          steps {
            git 'https://github.com/yohanwahyudi/spring-petclinic.git'
          }
        }
	stage('Build') {
            steps {
                sh 'mvn clean package -Dcheckstyle.skip'
				junit '**/target/surefire-reports/TEST-*.xml'
            }
        }

    }
}
