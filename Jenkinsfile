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
                deploy adapters: [tomcat9(credentialsId: 'tomcat_cred', path: '', url: 'http://54.188.141.133:8080/')], contextPath: null, onFailure: false, war: '**/*.war'            }
        }
        
       
    }
    
}

        
