pipeline {
    
    parameters {
  string defaultValue: 'defaultvalue', name: 'testArg'
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
        
        stage('Execute sh')
        
        {
            
            agent
            {
                label 'built-in'
            }
            steps
            {
            sh 'ls'
                sh 'chmod +x JenkinsTest.sh'
                sh './JenkinsTest.sh'
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
