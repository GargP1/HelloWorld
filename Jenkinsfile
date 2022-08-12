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
                sh 'rm -rf HelloWorld'
                sh 'git clone https://github.com/GargP1/HelloWorld.git -b env.BRANCH_NAME'
                sh 'cd HelloWorld'
                sh 'dotnet build'
                sh 'dotnet run --urls "http://0.0.0.0:5000" &'
        	}
            }
        }
    }
}
