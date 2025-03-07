pipeline {
    agent any 
    stages {
        stage("Download") {
            steps {
                cleanWs()
                sh """
                    sudo apt update
                    sudo apt install -y python3 python3-flask
                    mkdir app
                    cd app
                    wget https://raw.githubusercontent.com/alezxandro/python_jenkins_prova/main/webpage.py -O script.py
                """
            }
        }
        stage("TEST File") {
            steps {
                sh "ls -la app" // Controlla se il file esiste nella cartella corretta
                input "Vado avanti?"
            }
        }
        stage("TEST App") {
            steps {
                sh "python3 app/script.py" // Esegue il file dal percorso corretto
                input "Vado avanti?"
            }
        }
        stage("Done") {
            steps {
                echo "Applicativo funzionante ✅"
            }
        }
    }
}
