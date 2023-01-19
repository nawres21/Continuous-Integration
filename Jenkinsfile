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
                
             sh " mvn sonar:sonar -Dsonar.projectKey=sonarproject -Dsonar.host.url=http://http://172.26.23.115:9000/ -Dsonar.login=b7564d3e4c22cf5d705647316da196e286f2bab1"
 
            }
        }
        
        
    }}
