pipeline {
    agent any
    tools {
        maven 'Maven3.9.15'
        jdk 'jdk17'
    }

    stages {

        stage('Build') {
            steps {
                bat 'mvn install'
            }
            post {
                success{
                    junit 'target/surefire-reports/**/*.xml/'
                }
            }
        }

    }
}
