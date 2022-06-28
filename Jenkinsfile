pipeline{
    agent any
    
    stages{
        stage("git checkout")
        {
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '0146b7c3-f64c-4489-9763-af1242108a75', url: 'https://github.com/badam-nikitha/git_mvn_pipeline.git']]])
            }
        }
        stage("compile")
        {
            steps{
                sh "mvn compile"
            }
            
         }
            stage("Test")
            {
                steps{
                    sh "mvn test"
                }
            }
        stage("package")
        {
            steps{
                sh "mvn package"
            }
        }    
            

        
    }
}
