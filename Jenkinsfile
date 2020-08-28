def foo (name, command) {
    node {
        stage ("${name}") {
            checkout scm

            // Run docker with custom registry
            // https://www.jenkins.io/doc/book/pipeline/docker/

            docker.image("ubuntu:latest").inside {
                sh "echo 'Running command: ${command}'"
            }
        }
    }
}

pipeline {
    agent any
    stages {
        stage('Main') {
            steps {
                parallel {
                    script {
                        foo("Makefile", "make all")
                    }
                    script {
                        foo("Makefile", "make all")
                    }
                }
            }
        }
    }
}

