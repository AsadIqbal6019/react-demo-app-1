pipeline {
    agent any
     tools {
        nodejs 'Nodejs'
//         docker 'Docker-plugin'
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
//                 echo  DOCKER_CONTAINER_ID
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                // sh 'git clone "https://github.com/AsadIqbal6019/react-demo-app-1.git"'
                sh "rm -rf *.tar"
                sh "tar -czvf react-app-'$BUILD_NUMBER'.tar.gz *"
                sh "cp react-app-'$BUILD_NUMBER' ~/Music"
                sh "docker ps"
            }
        }
    }
}
