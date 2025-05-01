pipeline {
    agent any

    stages {
        stage('Initial Commit') {
            when {
                branch pattern: "main", comparator: "EQUALS"
            }
            steps {
                echo '📥 Initial commit logic executed (main branch only)'
            }
        }

        stage('Build') {
            steps {
                echo '🏗️ Building the project...'
            }
        }

        stage('Code Analysis') {
            steps {
                echo '🔍 Running code analysis tools...'
            }
        }

        stage('Artifact Upload') {
            steps {
                echo '📦 Uploading artifact to repository (simulated)...'
            }
        }

        stage('Deployment') {
            steps {
                echo '🚀 Deploying application (simulated)...'
            }
        }
    }
}
