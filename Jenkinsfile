pipeline {
    agent {
        docker{
            image 'ruby'
        }
    }
    
    stages {
        stage('build'){
            steps {
                echo 'Building or Resolve Dependencies !'
                sh 'bundle install'
            }
        }
        
        stage('Test'){
            steps {
                echo 'Running regression tests'
            }
        }
        
        stage('UAT'){
            steps{
                echo 'Wait for user acceptance'
                input(message: 'Go to production?', ok: 'Yes')
            }
        }
        
        stage('Prod'){
            steps {
                echo 'Webapp is ready :)'
            }
        }
    }
}