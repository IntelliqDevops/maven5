pipeline
{
    agent any
    stages
    {
        stage('Download_Master')
        {
            steps
            {
                git 'https://github.com/IntelliqDevops/maven.git'
            }
        }
        stage('Build_Master')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('Deployment_Master')
        {
            steps
            {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '8858849e-1322-4fbe-99e1-f194a326f772', path: '', url: 'http://172.31.20.22:8080')], contextPath: 'mytestapp', war: '**/*.war'
            }
        }
        stage('Testing_Master')
        {
            steps
            {
                git 'https://github.com/IntelliqDevops/FunctionalTesting.git'
                sh 'java -jar  /var/lib/jenkins/workspace/DeclarativePipeline1/testing.jar'
            }
        }
        stage('Delivery_Master')
        {
            steps
            {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '8858849e-1322-4fbe-99e1-f194a326f772', path: '', url: 'http://172.31.21.30:8080')], contextPath: 'myprodapp', war: '**/*.war'
            }
        }
    }
}

