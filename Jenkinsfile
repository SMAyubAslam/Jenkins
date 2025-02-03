pipeline {
    agent any
    environment{
        name = 'Ayub'
    }
    parameters{
        string(name: 'person', defaultValue: 'Ayub', description: 'Who are you?')
        booleanParam(name: 'IsMale' , defaultValue: true , description: "")
        choice(name: 'City' , choices: ['Karachi','Lahore','Islamabad'], description: "")
    }

    stages {
        stage('Run commands') {
            steps {
                sh '''
                ls
                date
                pwd
                '''
            }
        }
        stage('Environment Variable') {
            environment{
                username = 'asy1fr12'
            }
            steps {
               sh 'echo "${BUILD_ID}"'
               sh 'echo "${username}"'
            }
        }
        stage('Parameters') {
            steps {
                echo 'deploy on test'
                sh 'echo "${person}"'
            }
        } 
        stage('Continue') {
            input{ 
                message 'Should we continue?'
                ok 'We should'
            }
            steps {
                echo 'deploy on prod'
                
            }
        }
    }
}
