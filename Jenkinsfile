pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'cd /opt/java-maven-project && mvn clean package'
            }
        }

        stage('Verify WAR') {
            steps {
                sh 'ls -lh /opt/java-maven-project/target/myapp.war'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                sh '''
                    scp -i /var/lib/jenkins/.ssh/tomcat_deploy \
                    -o StrictHostKeyChecking=accept-new \
                    /opt/java-maven-project/target/myapp.war \
                    deploy@172.31.3.149:/var/lib/tomcat10/webapps/myapp.war
                '''
            }
        }

        stage('Verify Deployment') {
            steps {
                sleep 15
                sh 'curl -f http://172.31.3.149:8080/myapp/'
            }
        }
    }
}
