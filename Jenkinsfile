@Library('my-shared-library') _ 

pipeline {
    tools {
        maven 'mymaven'
    }
    agent linux_slave
    stages{
        stage ('Checkout code') {
            steps {
                cloneRepo('https://github.com/AVSLDOT/calcwebapp-sonar.git')                        }        
        }
        stage ('Build Code') {
            steps {
                build('Compile')
                
            }        
        }
        stage ('Check Logs') {
            steps {
                filterLogs('WARNING',2)
            }        
        }
    }
}
