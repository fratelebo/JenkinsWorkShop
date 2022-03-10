pipeline {
    
    parameters {
  string defaultValue: 'defaultvalue', name: 'testArg'
}


    agent any

    stages {
        stage('Clean workspace')
        {
            
            steps
            {
            cleanWs()
            }
            
            
        }
        
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh 'echo ${testArg}'
                sh 'echo "Added from geenrator"'
            }
        }
    }
}
