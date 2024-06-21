pipeline {
   agent {
        label 'AGENT-1'
   }

   options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'SECONDS')
    }
   stages {
      stage('Build') { 
          steps {
             sh 'echo this is build'
            }
        }
      stage('Test') { 
          steps {
             sh 'echo this is test'
            }
        }
      stage('Deploy') { 
          steps {
       sh 'echo this is deploy'
            }
        }
    }
}