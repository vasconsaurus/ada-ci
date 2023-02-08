pipeline {
    agent {label 'nodoprojeto'}

    options {
    ansiColor('xterm')
    }

    stages {
        stage('Clone repository') {
            steps {
              git (
                branch: 'main',
                url: 'https://github.com/vasconsaurus/ada-ci.git' 
              )
              sh "echo '\033[37;44;1mAccessingGitHub\033[0m'"
            }
        }


        stage('Build dev'){
            when {
               not {
                  branch "main"
               }
            }
            steps {
                script{
                 image = docker.build("vasconsaurus/v1:develop")
                }
                sh "echo '\033[37;44;1mBuildingImageOnDevelop\033[0m'"
            }
        }
        stage('Build') {
            when {
                branch "main"
            }
            steps {
                script{
                 image = docker.build("vasconsaurus/v1:main")
                }
                sh "echo '\033[37;44;1mBuildingImageOnMain\033[0m'"
            }
        }
        stage('Push') {
            steps {
                script{
                       docker.withRegistry('', 'docker-hub') {
                       image.push()
                    }
                }
                sh "echo '\033[37;44;1mPushingToDockerHub\033[0m'"
            }
        }
        stage('Deploy') {
            steps {
                 script {
                    docker.image('vasconsaurus/v1:main').withRun('-p 3000:3000 -d') {c ->
                        sleep 300
                    }
                }
                sh "echo '\033[37;44;1mDeployingLocally\033[0m'"
            }
        }

        
    }
}


