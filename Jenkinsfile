pipeline {
    agent any
    parameters {
      string(name:'Branch', defaultValue:'master', description:'enter branch to build')
}
    tools{
        maven 'maven-3.9.0'
    }
    stages {
        stage("Checkout the project") {
            steps {
                git branch: '${Branch}', url: 'https://github.com/Bytesrite-Technologies/hello-maven-ibt.git'
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
        stage ("Static Code Analysis") {
            environment{
             scannerHome = tool 'ibt-sonarqube';
    }
       steps{
        withSonarQubeEnv(credentialsId:'SQ-student' installationName:'IBT sonarqube')) {
        sh "$scannerHome/bin/sonar-scanner -Dsonar.projectKey=Jan26_cohort"
}


}

