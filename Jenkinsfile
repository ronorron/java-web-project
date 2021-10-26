pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh 'mvn -DskipTests clean package'
            }
        }
        stage("Deploy"){
            steps{
               deploy adapters: [tomcat7(credentialsId: '3a93afd7-d538-4a6c-8b13-3e4146650e88', path: '', url: 'http://ec2-3-83-212-150.compute-1.amazonaws.com:8080/')], contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
