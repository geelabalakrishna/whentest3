pipeline {
    agent any

    stages {
        stage('Build & Unit Test') {
            when {
                anyOf {
                    branch 'dev'
                    branch 'test'
                    branch 'preprod'
                    branch 'prod'
                    branch pattern: "feature/.*", comparator: "REGEXP"
                }
            }
            steps {
                echo "🛠️ Building and running unit tests"
            }
        }

        stage('Code Analysis') {
            when {
                branch pattern: "feature/.*", comparator: "REGEXP"
            }
            steps {
                echo "🔍 Running code quality checks"
            }
        }

        stage('Deploy to Dev') {
            when {
                branch 'dev'
            }
            steps {
                echo "🚀 Deploying to DEV environment"
            }
        }

        stage('Deploy to Test') {
            when {
                branch 'test'
            }
            steps {
                echo "🧪 Deploying to TEST environment"
            }
        }

        stage('Deploy to PreProd') {
            when {
                branch 'preprod'
            }
            steps {
                echo "📦 Deploying to PREPROD"
            }
        }

        stage('Deploy to Prod') {
            when {
                branch 'prod'
            }
            steps {
                echo "✅ Deploying to PRODUCTION"
            }
        }
    }
}
