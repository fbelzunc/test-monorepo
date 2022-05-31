pipeline {
    agent none
    stages {
        stage('Build Frontend') {
            agent { label 'default-java' }
            when {
                changeset "**/frontend/*.*"
                beforeAgent false
            }
            steps {
                dir('frontend') {
                  sh 'echo Hello Build Frontend!'
                }
            }
        }
        stage('Build Web') {
            agent { label 'default-java' }
            when {
                changeset "**/backend/web/*.*"
                beforeAgent false
            }
            steps {
               dir ('backend/web') {
                sh 'echo Hello Build Web!'
               }
            }
        }
        stage('Build REST API') {
            agent { label 'default-java' }
            when {
                changeset "**/backend/api/*.*"
                beforeAgent false
            }
            steps {
               dir ('backend/api') {
                 sh 'echo Build REST API!'
               }
            }
        }
    }
}
