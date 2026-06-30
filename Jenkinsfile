pipeline{
    agent any
    stages{
        stage('build maven')
        {
            steps{
                sh './mvnw clean package'
            }
        }
        stage('build docker image')
        {
                steps{
                    sh 'docker build -t venkat664/spring-app1:v1 .'
                }
        }
        // stage('deploy')
        // {
        //     steps{
        //         sh 'docker service create --name spring-app --replicas 2 -p 8081:8081 spring-app:v1'
        //     }
        // }
        stage('docker hub push')
        {
            steps{
                sh ' echo "venkat1438" | docker login -u venkat664 -p --password-stdin'
                sh 'docker push venkat664/spring-app1:v1'
            }

        }

    }
}