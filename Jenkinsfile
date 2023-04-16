pipeline{
    agent{
        label "jenkins-worker-1"
    }
    tools{
        maven'MAVEN_HOME'
    }
    stages{
        stage("Pull the Code From SCM"){
            steps{
                echo "==============Pull the Code From SCM=========="
                git branch: 'main',
                    url: 'https://github.com/Umamahesh3456/weshopify-service-registry.git'
                echo "Source code Pulling is completed"
            }
        }
        stage("Build the Source code"){
            steps{
                echo "=======Code Building is Starting==========="
                sh 'cd weshopify-platform-services-registry && mvn clean verify sonar:sonar -Dsonar.projectKey=weshopify-service-registry -Dsonar.host.url=http://65.0.152.251:9000 -Dsonar.login=sqp_d703e6006ac8caa15c76832988cc76dd551c6869 -DskipTests=true'
                sh 'cd weshopify-platform-services-registry && mvn deploy'
                echo "=======Code Building is Completed==========="
            }
        }
    }
}
