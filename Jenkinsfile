pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                script {
                    git branch: 'main', changelog: false, poll: false, url: 'https://github.com/bhavani467/student-managementsystem.git'
                }
            }
        }
        stage('build') {
            steps {
                script {
                    bat 'mvn clean install'
                }
            }
        } 
		stage('deploy'){
		    steps {
			     script {
				    bat 'cp C:/ProgramData/Jenkins/.jenkins/workspace/student management system/target/student-management-0.0.1-SNAPSHOT.jar  D:/apache-tomcat-9.0.89/webapps/ROOT.jar'
				}
			}
		}
    }
}
