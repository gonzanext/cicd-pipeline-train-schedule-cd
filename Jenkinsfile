pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        stage('Stage') {
            when {
                branch 'master'
            }
            steps {
                echo 'Deploying to Stage...'
                
            }          
        }
        stage('Production') {
            when {
                branch 'master'
            }
            steps {
                echo 'Deploying to Production...'                
            }          
        }            
    }
}
