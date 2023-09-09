pipeline{
    agent any
    tools {
        maven 'maven-3.6.3'
    }
    stages{
        stage('maven test'){
            steps{
                sh 'mvn clean test'
            }
        }
    
        stage('maven package'){
            steps{
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage("sonarqube build"){
            steps{
                withSonarQubeEnv('kiran') {
                    sh "mvn clean package sonar:sonar"
                }
            }
        }
        
    }
}