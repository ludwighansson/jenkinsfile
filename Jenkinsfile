pipeline {
    agent {
        docker {
            image 'ubuntu:latest'
        }
    }
    stages {
        stage('build') {
            steps {
                generateStage("build")
            }
        }
    }
}

def generateStage(bar) {
    return {
        stage("Build ${bar}") {
            echo "Building for ${bar}"
        }
    }
}