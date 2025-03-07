pipeline {
    agent any 
    stages {
        stage("Download") {
            steps {
                cleanWs()
                sh "apt install python3 python3-flask"
                sh "mkdir app"
                sh "cd app"
                sh "wget https://raw.githubusercontent.com/alezxandro/python_jenkins_prova/refs/heads/main/webpage.py -O script.py"
            }
        }
        stage("TEST File") {
            steps {
                sh "cd app"
                sh "ls app"
                input "vado?"
            }
        }
        stage("TEST App"){
            steps {
                sh "python3 script.py"
                input "vado?"
            }
        }
        stage("Done") {
            steps {
                echo "Applicativo funzionante"
            }
        }
    }
}
