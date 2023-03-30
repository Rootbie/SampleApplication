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
                
                deploy adapters: [tomcat9(credentialsId: 'tomcat-dangnhap', path: '', url: 'http://127.0.0.1:8090/')], contextPath: 'anhdo', war: '**/*.war'
            }
        }
    }
}
