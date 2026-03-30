pipeline {
    agent { 
        node {
            label 'docker-agent-python'  // This label should match the label of the agent you want to run this pipeline on
            }
      }
    triggers {
        pollSCM('*/5 * * * *')   // Polls the SCM every 5 minutes for changes
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.." // we need to ensure the fire library is installed in the agent, so we can run the hello.py file
                sh '''
                cd myapp
                pip install -r requirements.txt  
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Siya
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                python3 hello.py
                '''
            }
        }
    }
}