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
    }
}
