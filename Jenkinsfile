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
       
        
        
        
        
    }
}
