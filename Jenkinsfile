pipeline {
    agent any
     tools {
  maven 'M2_HOME'
}
triggers {
pollSCM ('* * * * *')
} 
    
    stages {
        stage('maven package') {
            steps {
                sh 'mvn clean'
                sh 'mvn install'
                sh 'mvn package'
                sleep 5
            }
        }
          stage('test') {
            steps {
                sh 'mvn test'
                sleep 5
            }
        }
          stage('deploy') {
            steps {
                echo 'Deploy step'
                sleep 4
            }
        }
          stage('Docker') {
            steps {
                echo 'Image step'
                sleep 4
            }
        }
    }
}
