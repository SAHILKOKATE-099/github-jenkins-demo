pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat '"C:\\Users\\Admin\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" build -t github-jenkins-demo .'
            }
        }

        stage('Deploy') {
            steps {
                bat '"C:\\Users\\Admin\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" rm -f github-jenkins-demo'
                bat '"C:\\Users\\Admin\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" run -d --name github-jenkins-demo -p 5000:5000 github-jenkins-demo'
            }
        }
    }
}
