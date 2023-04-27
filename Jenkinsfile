pipeline {
    agent any
     tools {
        nodejs 'Nodejs'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'npm install'
                sh 'npm run build'

            }
        }
        stage('Test') {
            steps {
                echo 'Testing the web Application'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                // sh 'git clone "https://github.com/AsadIqbal6019/react-demo-app-1.git"'
                sh "tar -czvf react-app-1-$BUILD_NUMBER.tar.gz /var/jenkins_home/workspace/react-app-demo-1"
            }
        }
    }
}