pipeline{
    agent any
    environment {
        root = "/usr/local/go/bin/go"
        branch = "master"
        scmUrl = "https://github.com/pradwi17/sample-go-jenkins.git"
        modName = "sample-go-jenkins"
        port = "8082:8082"
    }

    stages{
        stage("Go Version"){
            steps{
                sh "${root} version"
            }
        }

        stage("Git Clone"){
            steps{
                git branch: "${branch}", url: "${scmUrl}"
            }
        }

        stage("Docker Build"){
            steps{
                sh "sudo -S docker build -t ${modName} ."
            }
        }

        stage("Docker Password"){
            steps{
                sh "12345678"
            }
        }

        stage("Docker Run"){
            steps{
                sh "sudo -S docker run --name my-gojenkins -p ${port} ${modName}"
            }
        }                   
    }
}