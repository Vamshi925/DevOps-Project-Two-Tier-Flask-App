pipeline{
    agent any{
        stages{
            stage('Clone repo'){
                step{
                    git branch: 'main' , url: 'https://github.com/Vamshi925/DevOps-Project-Two-Tier-Flask-App.git'
            }
        }
        stage('Build Image'){
                step{
                    sh 'docker build -t flask-app .'
            }
        }
        stage('Deploy with docker compose'){
                step{
                    sh 'docker compose down || true'

                    sh 'docker compose up -d --build'
            }
        }
    }
}
}