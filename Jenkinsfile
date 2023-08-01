
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'echo "Building the project..."'
                // Add build commands here (e.g., 'mvn clean package' for Maven projects)
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Running unit tests..."'
                // Add test commands here (e.g., 'mvn test' for Maven projects)
            }
        }

        stage('Archive Artifacts') {
            steps {
                sh 'echo "Archiving build artifacts..."'
                archiveArtifacts 'target/*.jar' // Example: Archive all JAR files in the 'target' directory
            }
        }

        stage('Deploy to Staging') {
            when {
                branch 'master' 
            }
            steps {
                sh 'echo "Deploying to staging environment..."'
                
            }
        }

        stage('Deploy to Production') {
            when {
                branch 'develop' 
            }
            steps {
                sh 'echo "Deploying to production environment..."'
                
            }
        }
    }
}
