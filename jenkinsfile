pipeline {
    agent any

    stages {
        stage('Test Build Stage') {
            steps {
                echo 'Hello from the build stage.'
            }
        }
        stage('Test Test Stage') {
            agent {
                docker { image 'alpine:latest' }
            }
            steps {
                echo 'Hello from the test stage running on alpine.'
            }
        }
        stage('Test Deploy Stage') {
            agent {
                docker { image 'ubuntu:latest' }
            }
            steps {
                sh 'echo \"Hello from the deploy stage running on ubuntu.\" > test.txt'
                sh 'cat test.txt'
            }
        }
    }

    // Next step, having pipeline pull bitbucket/github project for use
    // From there move onto data peristence between stages/logging stage results in meaningful fashion

}
