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

          stage ("Sonar Quality Check") {
           steps {
           withSonarQubeEnv(credentialsId:'jenkins-sonar-token', installationName:'sonar-9') {
           sh 'mvn sonar:sonar'


        stage ("Build the package") {
            steps {
                sh 'mvn clean package'
        }

          
}


}
}
}
