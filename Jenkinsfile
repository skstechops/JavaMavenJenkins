pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('List Java Files') {
            steps {
                sh '''
                    echo "Java files in the application:"
                    find src/main/java -type f -name "*.java"
                '''
            }
        }

        stage('Test') {
            steps {
                sh 'mvn clean test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package -DskipTests'
            }
        }

        stage('List JAR Files') {
            steps {
                sh '''
                    echo "JAR files generated:"
                    find target -type f -name "*.jar"
                '''
            }
        }

    }
}


