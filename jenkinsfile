pipeline {
    agent any 
    stages {
        stage('we r Compiling') { 
            steps {
                sh "mvn compile"
            }
        }
		stage('we r CodeReviewing') { 
            steps {
              	sh "mvn -P metrics pmd:pmd"
            }
        }
		stage('we r Testing') { 
            steps {
              		sh "mvn test"
            }
        }
		stage('we r MetricChecking') { 
            steps {
              	sh "mvn mvn cobertura:cobertura -Dcobertura.report.format=xml"
            }
        }
        stage('we are Packaging') { 
            steps {
                sh "mvn mvn package"
            }
        }
        }
}

