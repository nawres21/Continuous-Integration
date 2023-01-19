pipeline{
    agent any
   
    stages {
        stage('Getting project from Git') {
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], browser: [$class: 'GithubWeb', repoUrl: 'https://github.com/nawres21/Continuous-Integration.git'], extensions: [], userRemoteConfigs: [[credentialsId: 'ws.id', url: 'https://github.com/nawres21/Continuous-Integration.git']]])
            }
        }
        stage('Cleaning the project') {
            steps{
                sh "mvn -B -DskipTests clean  " 
            }
        }
        
        stage('Code Quality Check via SonarQube') {
            steps{
                
             sh " mvn sonar:sonar -Dsonar.projectKey=CICD_Academic_Project -Dsonar.host.url=http://localhost:9000 -Dsonar.login=5f74b4c464cd1ad62d859b40eb6c42eda392d71e"
 
            }
        }
        
        
    }}
