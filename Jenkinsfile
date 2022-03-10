pipeline {
    
    parameters {
  string defaultValue: 'defaultvalue', name: 'testArg'
         string defaultValue: 'production', name: 'DEPLOY_TO'
}


    agent any

    stages {
       
        
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh 'echo ${testArg}'
                sh 'echo "Added from geenrator"'
            }
        }
        
        stage('Execute sh in prod')
        
        {
            when {
             
                environment name: 'DEPLOY_TO', value: 'production'
            }
            
            agent
            {
                label 'built-in'
            }
            steps
            {
                sh 'echo VEZI CA DAI IN PROD'
            sh 'ls'
                sh 'chmod +x JenkinsTest.sh'
                sh './JenkinsTest.sh'
            }
        
        }
        
        
        
         stage('Execute sh in sandbox')
        
        {
            when {
             
                environment name: 'DEPLOY_TO', value: 'sandbox'
            }
            
            agent
            {
                label 'built-in'
            }
            steps
            {
            sh 'ls'
            sh 'echo VEZI CA DAI IN SANDBOX'
            }
        
        }
        
        stage('Example Deploy') {
            when {
                anyOf {
                    environment name: 'DEPLOY_TO', value: 'production'
                    environment name: 'DEPLOY_TO', value: 'sandbox'
                    environment name: 'testArg', value: 'defaultvalue'
                }
            }
            steps {
                echo 'asta se executa oricand se alege prod/sandbox/defaultvalue '
            }
        }
        
         stage('Clean workspace')
        {
            
            steps
            {
            cleanWs()
            }
            
            
        }
        
        
    }
}
