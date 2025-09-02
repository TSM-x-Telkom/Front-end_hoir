pipeline {
    agent any

    tools {
        nodejs "NodeJS_24"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'git@github.com:TSM-x-Telkom/Front-end_hoir.git',
                    credentialsId: 'ssh-github-key'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Lint') {
            steps {
                sh 'npm run lint || true'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        // Stage Deploy bisa ditambahkan nanti ketika SSH server siap
        // stage('Deploy') {
        //     steps {
        //         sh 'echo "Deploy nanti setelah SSH server siap"'
        //     }
        // }
    }
}

