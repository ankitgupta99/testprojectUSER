pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
				withmaven(maven: 'maven'){
				sh 'mvn clean compile'
            }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
				withmaven(maven: 'maven'){
				sh 'mvn test'
            }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
				withmaven(maven: 'maven'){
				sh 'mvn deploy'
            }
            }
        }
    }
}
