pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    git branch: 'main', changelog: false, poll: false, url: 'https://github.com/bhavani467/student-managementsystem.git'
                }
            }
        }
        stage('Build') {
            steps {
                script {
                    bat 'mvn clean install'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    def jarPath = "${env.WORKSPACE}\\target\\student-management-0.0.1-SNAPSHOT.war"
                    def destinationPath = "D:\\apache-tomcat-9.0.89\\webapps\\student-management-0.0.1-SNAPSHOT.war"
                    bat "copy \"${jarPath}\" \"${destinationPath}\""
                }
            }
        }
    }
}
