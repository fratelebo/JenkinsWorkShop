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
    }
}
