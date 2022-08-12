pipeline {
    agent any
       triggers {
        pollSCM "* * * * *"
       }
    stages {
        stage('Build and Deploy') {
            steps {
                echo '=== Connect to Server, Build and Deploy ==='
        	sshagent(credentials : ['ssh-to-server']) {
                sh 'git clone https://github.com/GargP1/HelloWorld.git'
        	}
            }
        }
    }
}
