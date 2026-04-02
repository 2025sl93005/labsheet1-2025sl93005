pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Checking out source code"
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Build stage"
                sh 'ls -l'
                sh 'python3 --version'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests"

                sh '''
                python3 - <<EOF
import calculator

assert calculator.add(2,3) == 5
assert calculator.sub(5,3) == 2
assert calculator.mul(2,3) == 6
assert calculator.div(6,3) == 2

print("All tests passed")
EOF
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploy stage placeholder"
            }
        }

    }
}
