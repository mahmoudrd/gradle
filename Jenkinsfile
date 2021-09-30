pipeline {
    
    agent any
    
    stages{
        stage('init'){
            steps {
                script {
                   gv = load "groovy.script" 
                }
            }
        }
        
        stage('Setup Parameters') {
            steps {
                script {
                    gv.param()
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
                    gv.build()
                }
            }
        }
    }
}
