pipeline
{
    agent any
    stages
    {
        stage('Download_Loans')
        {
            steps
            {
                git 'https://github.com/IntelliqDevops/maven.git'
            }
        }
        stage('Build_Loans')
        {
            steps
            {
                sh 'mvn package'
            }
        }
   }
   }
