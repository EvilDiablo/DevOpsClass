pipeline{
    agent any
    triggers{
        pollSCM '*/5 * * * *'
    }
    stages{
        stage('Build'){
            steps{
                sh '''
                apt update
                apt upgrade -y
                apt-get install python3 -y
                apt-get install python3-venv -y
                apt install python3-pip -y
                python3 -v
                python3 -m venv .venv
                . .venv/bin/activate
                '''
            }
        }
        stage('Test'){
            steps{
                sh '''
                python3 main.py
                '''
            }
        }

        stage('Deploy'){
            steps{
                sh '''
                echo "It Done"
                '''
            }
        }
    }
}