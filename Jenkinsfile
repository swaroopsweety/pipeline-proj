pipeline {
    agent any

    stages {
        stage('continuous download') {
            steps {
                git 'https://github.com/mgsgoms/vanakkam-world.git'
            }
        }
        stage('continuous build') {
            steps {
                sh 'mvn install'
            }
        }
        stage('continuous deploy') {
            steps {
                sh 'sshpass -p "jeevan" scp webapp/target/webapp.war jeevan@172.17.0.4:/opt/apache-tomcat-9.0.56/webapps'
            }
        }
    }
}

