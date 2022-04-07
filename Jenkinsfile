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
                sh "docker build -t ${modName} ."
            }
        }

        stage("Docker Run"){
            steps{
                sh "docker run --name my-gojenkins -p ${port} ${modName}"
            }
        }                   
    }
}