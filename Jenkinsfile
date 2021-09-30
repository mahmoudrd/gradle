pipeline {
    
    agent any
    
    stages{
        
        stage('Setup Parameters') {
            steps {
                script {
                    properties([
                        parameters([booleanParam('CREATE_JAR')
                        ])
                    ])
                }                
            }
        }
        //
        stage('Clone from Github') {
            steps {
                git branch: 'main', url:'https://github.com/spring-guides/gs-gradle.git'
            }
        }
        //
        stage('Build the Code') {
   
            steps{
                script{
                if (params.CREATE_JAR) {
                    dir('complete') {
                        sh "./gradlew clean jar"
                    }
                } else {
                    dir('complete') {
                        sh "./gradlew clean build"
                    }
                }
            }
            }
        }
    }
}
