pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Unit Tests') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts 'target/*.jar'
            }
        }

        stage('Deploy to Staging') {
            when {
                branch 'staging'
            }
            steps {
                // Add deployment steps for the staging environment here
            }
        }

        stage('Deploy to Production') {
            when {
                branch 'production'
            }
            steps {
                // Add deployment steps for the production environment here
            }
        }
    }
}
