pipeline {
    agent {
        docker{
            image 'can8/rubywd'
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
                sh 'bundle exec cucumber'
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