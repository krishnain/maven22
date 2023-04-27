pipeline
{
    agent any
    stages
    {
        stage('ContDownload')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'
            }
        }
        stage('ContBuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('ContDeployment')
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '5b13cc61-42a6-4cf8-a777-e270e1af1971', path: '', url: 'http://172.31.31.39:8080')], contextPath: 'test1', war: '**/*.war'
            }
        }
        stage('ContTesting')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
            }
        }
        stage('ContDelivery')
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '5b13cc61-42a6-4cf8-a777-e270e1af1971', path: '', url: 'http://172.31.20.75:8080')], contextPath: 'prod1', war: '**/*.war'
            }
        }
        
        
        
        
    }
}
