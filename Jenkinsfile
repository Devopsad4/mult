pipeline
{
    agent any
    stages
    {
        stage('COntinuous Download')
        {
            steps
            {
                git 'https://github.com/Devopsad4/jio.git'
            }
        }
        stage('Continuous Build')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('Continuous Deploy')
        {
            steps
            {
                sh 'scp /home/ubuntu/.jenkins/workspace/df/webapp/target/webapp.war ubuntu@172.31.82.252:/var/lib/tomcat9/webapps/testapp.war'
            }
        }
        stage('Continuous Testing')
        {
            steps
            {
                git 'https://github.com/Devopsad4/FunctionTesting.git'
                sh 'java -jar /home/ubuntu/.jenkins/workspace/df/testing.jar'
            }
        }
        stage('Continuous Delivery')
        {
            steps
            {
                sh 'scp /home/ubuntu/.jenkins/workspace/df/webapp/target/webapp.war ubuntu@172.31.87.145:/var/lib/tomcat9/webapps/prodapp.war'
            }
        }
        
        
        
        
    }
}
