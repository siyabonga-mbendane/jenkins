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
                echo "Building.."
                sh '''
                echo "doing build stuff.."
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                echo "doing test stuff.."
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}