pipeline {
   agent {
        label 'AGENT-1'
   }

    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
    }

   parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
   environment{
            DEPLOY_TO = 'DEV'
            GREETING = 'DEPLOYED TO DEV'
        }

   stages {
      stage('Build') { 
          steps {
             sh 'echo this is build'
             sh 'env'
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

      stage("print params"){
        steps{
            
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"

                echo "SUCCESSFULLY TRIGGERED!! WEBHOOK!!"
            }
        }

      }

      post{
        always{
            echo 'I will always say hello again'
        }
        success{
            echo 'I will say hello only when success'
        }
        failure{
            echo 'I will say hello only when failure'
        }
      }
    }
