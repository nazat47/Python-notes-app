@Library("Shared") _
pipeline{
    agent { label "vinod" }
    stages{
        stage("hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code"){
            steps{
                script{
                    gitclone("https://github.com/LondheShubham153/django-notes-app.git","main")
                }
            }
        }
        stage("Build"){
              steps{
                script{
                    build("notes-app","latest","nazatmustag")
                }
            }
        }
        stage("Push to docker hub"){
              steps{
                script{
                    dockerpush('notes-app','latest')
                }
            }
        }
        stage("Deploy"){
              steps{
                sh "docker compose up -d"
            }
        }
    }
}
