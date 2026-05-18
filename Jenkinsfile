pipeline {

    agent any

    tools {
        maven 'Maven3.9.15'
        jdk 'jdk17'
    }

    stages {

        stage('Build') {

            steps {
                bat 'mvn compile'
            }
        }

        stage('Tests') {

            steps {
                bat 'mvn test'
            }

            post {

                always {
                    junit 'target/surefire-reports/**/*.xml'
                }
            }
        }
        stage('Couverture') {

            steps {
                bat 'mvn jacoco:report'
            }
        }
        stage('Documentation') {

            steps {
                bat 'mvn javadoc:javadoc'
            }
        }
        stage('Packaging') {

            steps {
                bat 'mvn package'
            }
        }
        
        stage('Deploy') {
        
            steps {
                bat 'mvn deploy'
            }
        }
    }
}
