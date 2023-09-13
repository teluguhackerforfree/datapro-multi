pipeline {
    agent any

    stages {
        stage('git checkout') {
            steps {
                echo 'download source code'
				git 'https://github.com/teluguhackerforfree/maven.git'
            }
        }
		stage('compile') {
            steps {
                echo 'compiling maven package'
				sh 'mvn compile'
            }
        }
		stage('package') {
            steps {
                echo 'creating package'
				sh 'mvn package'
            }
        }
		stage('deploy') {
            steps {
                echo 'Hello World'
				deploy adapters: [tomcat9(credentialsId: 'tomcat-credential', path: '', url: 'http://20.232.24.49:8081/')], contextPath: 'dev', war: '**/*.war'
				
            }
        }
    }
}
