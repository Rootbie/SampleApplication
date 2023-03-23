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
                deploy adapters: [tomcat9(credentialsId: 'tomcat-login', url: 'http://127.0.0.1:8090')], contextPath: 'tomcat', war: '**/*.war'   
            }
        }
    }
}
