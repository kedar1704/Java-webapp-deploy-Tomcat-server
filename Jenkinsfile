pipeline 
{
    agent any

    stages {
        
        stage('Pull code from git'){
            steps{
                git branch: 'main', url: 'https://github.com/kedar1704/Java-webapp-deploy-Tomcat-server.git'
            }
        }
        
        stage('Clean Compile') {
            steps {
                sh "mvn clean compile"
            }
        }
        
        stage('Install') {
            steps {
                sh "mvn install"
            }
        }
        
         stage('Push artifact to tomcat server'){
            steps {
                deploy adapters: [tomcat7(credentialsId: 'final', path: '', url: 'http://52.33.39.138:8080/')], contextPath: null, war: '**/*.war'        
            }
         }
       
    }
    
}

        
