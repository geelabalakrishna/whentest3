pipeline {
    agent any

    stages {
        stage('Build') {
            when {
                anyOf {
                    branch pattern: "feature/.*", comparator: "REGEXP"
                    branch 'test'
                
                }
            }
            steps {
                echo "🛠️ code build"
            }
        }
        stage('Unit Test') {
            when {
                anyOf {
                    branch pattern: "feature/.*", comparator: "REGEXP"
                    branch 'test'
                
                }
            }
            steps {
                echo "🛠️ Unit Test"
            }
        }        

        stage('Code Analysis') {
            when {
                branch pattern: "test", comparator: "EQUALS"
            }
            steps {
                echo "🔍 Running code quality checks"
            }
        }

        stage('Deploy to Dev') {
            when {
                branch pattern: "feature/.*", comparator: "REGEXP"
            }
            steps {
                echo "🚀 Deploying to DEV environment"
            }
        }

        stage('Deploy to Test') {
            when {
                branch pattern: "test", comparator: "EQUALS"
            }
            steps {
                echo "🧪 Deploying to TEST environment"
            }
        }

        stage('Deploy to PreProd') {
            when {
                branch pattern: "preprod", comparator: "EQUALS"
            }
            steps {
                echo "📦 Deploying to PREPROD"
            }
        }

        stage('Deploy to Prod') {
            when {
                branch pattern: "prod", comparator: "EQUALS"
            }
            steps {
                echo "✅ Deploying to PRODUCTION"
            }
        }
    }
}
