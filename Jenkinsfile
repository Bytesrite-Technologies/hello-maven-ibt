pipeline {
    agent any
    tools{
        maven 'maven_3.8'
    }
    stages {
        stage("Checkout the project") {
            steps {
                git branch: 'master', url: 'https://github.com/IBT-learning/hello-maven.git'
            }
            }
        
        stage ("Validate the source code") {
            steps {
                sh 'mvn validate'
            }
        }
        
        stage ("Compile the source code") {
            steps {
                sh 'mvn compile'
            }
        }
       

        stage ("Build the package") {
            steps {
                sh 'mvn clean package'
        }
        }
    }
}

