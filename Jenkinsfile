@Library("shared") _

pipeline {
    agent { label "vyshu" }

    stages {

        stage("Hello") {
            steps {
                script {
                    hello()
                }
            }
        }

        stage("Code") {
            steps {
                script {
                    clone(
                        "https://github.com/Vyshnavi262007/django-notes-app.git",
                        "main"
                    )
                }
            }
        }

        stage("Build") {
            steps {
                script {
                    docker_build(
                        "notes-app",
                        "latest",
                        "vyshnavi262007"
                    )
                }
            }
        }

        stage("Push") {
            steps {
                script {
                    docker_push(
                        "notes-app",
                        "latest",
                        "vyshnavi262007"
                    )
                }
            }
        }

        stage("Deploy") {
           steps {
             script {
                 docker_deploy()
        }
    }
}
}
}
