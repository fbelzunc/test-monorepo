pipeline {
    agent none
    stages {
        stage('Build Frontend') {
            agent { label 'default-java' }
            when {
                changeset "**/frontend/*.*"
                beforeAgent true
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
                beforeAgent true
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
                beforeAgent true
            }
            steps {
               dir ('backend/api') {
                 sh 'echo Build REST API!'
               }
            }
        }
    }
}
