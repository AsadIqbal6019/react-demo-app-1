pipeline {
    agent any
     tools {
        nodejs 'Nodejs'
        // Docker 'Docker'
    }

     environment {          
        deploy_cmd = "/home/ubuntu/react-demo-app-1/deployment.sh"
        // deploy_cmd = "/var/jenkins_home/workspace/react-app-demo-1/deployment.sh"
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                // sh 'npm install'
                // sh 'npm run build'
                // sh 'npm install -g pm2'
                // sh 'pm2 start app.config.json && pm2 list'

            }
        }
        stage('Test') {
            steps {
                echo 'Testing the web Application'
            //    echo  DOCKER_CONTAINER_ID
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                // sh 'git clone "https://github.com/AsadIqbal6019/react-demo-app-1.git"'
                // sh "rm -rf *.tar"
                // sh "tar -czvf react-app-'$BUILD_NUMBER'.tar.gz *"
                //  sh "cp react-app-'$BUILD_NUMBER'.tar.gz ~/Music"
                // sh "docker exec -it fde77e00f7ed /bin/bash"
                // sh "docker cp fde77e00f7ed:/var/jenkins_home/workspace/react-app-demo-1 ~/Music"
                //  sh "ls"
                // sh "docker ps"
                // ssh -i "Asad-key-pair.pem" ubuntu@ec2-54-196-190-10.compute-1.amazonaws.com
                    sshagent(credentials: ['ec2-server-key']) {
                        sh "ssh -o StrictHostKeyChecking=no ubuntu@54.196.190.10 '\n' chmod +x /home/ubuntu/react-demo-app-1/deployment.sh '\n' ${deploy_cmd}"
                        sh "pwd"
                    }
                    // sshagent(credentials: ['ec2-server-key']) {
                    //     sh "ssh -o StrictHostKeyChecking=no ubuntu@54.204.161.188 '\n' pwd '\n' git clone https://github.com/AsadIqbal6019/react-demo-app-1.git '\n' cd react-demo-app-1 '\n' npm install '\n' npm run build"
                    //     sh "pwd"
                    //     // sh "cd /home/ubuntu"
                    //     // sh "mkdir app1"
                    // }
                
                echo 'Done'

        }
    }
}
}
