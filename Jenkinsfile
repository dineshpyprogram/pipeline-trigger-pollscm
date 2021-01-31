pipeline {
    agent any
    options {
        timestamps()
    }
    triggers {
        pollSCM("* * * * *")
    }

    stages {
        stage("build") {
            steps {
                checkout([$class: "GitSCM",
                branches: [[name: "origin/master"]],
                userRemoteConfigs: [[
                    url: "https://github.com/dineshpyprogram/pipeline-trigger-pollscm.git"]]])

                echo "printenv"
                sh printenv
                
            }
        }
    }
}