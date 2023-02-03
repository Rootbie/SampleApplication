pipeline {
    agent any

    tools {
        maven 'maven'   
    }
//     triggers{
//         githubPush()
//     }
    
    stages{
        stage("Build"){
            steps{
                sh "mvn clean package"
            }
        }

        stage("Deploy"){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'd667366f-072f-4bcc-83a3-cc6eeb608490', url: 'http://3.35.24.233:8090')], contextPath: 'tomcat path', onFailure: false, war: '**/*.war'   
            }
        }
    }
}
