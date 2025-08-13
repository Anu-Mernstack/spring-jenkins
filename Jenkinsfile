pipeline {
    agent any
    tools {
        maven 'Maven 3.9.11'
        jdk 'JDK 21'
    }
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Package') {
            steps {
                bat 'mvn package -DskipTests'
            }
        }
        stage('Deploy') {
            steps {
                bat '''
                for %%f in (target\*.jar) do (
                    java -jar %%f
                )
                '''
            }
        }
    }
}
