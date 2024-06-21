pipeline {
   agent {
        label 'AGENT-1'
   }

   parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

   options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
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