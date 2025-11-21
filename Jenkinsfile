pipeline{
    agent any
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
                    //existing container if they are running
                    sh 'docker compose down || true'
                    // start app, rebuilding flask image
                    sh 'docker compose up -d --build'
            }
        }
    }
}
