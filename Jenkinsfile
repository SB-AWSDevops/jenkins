pipeline {
   agent {
        label 'AGENT-1'
   }

   options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 5, unit: 'SECONDS')
    }
   stages {
      stage('Build') { 
          steps {
             sh 'echo this is build'
             sh 'sleep 10'
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