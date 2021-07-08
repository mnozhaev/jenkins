pipeline {
    agent any
    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    parameters{
        choice(name: 'VERSION',choices:['1.1','1.2','2.0','2.2'],description:'version')
        booleanParam(name: 'executedTests', defaultValue: true , description: 'executedTests')
    }
    
    stages {
       
        stage("init") {
             
            steps {
                script {
                   gv = load "script.groovy" 
                }
            }
                
               script{

                   gv =load "script.groovy"
               }
           }
        }
        stage("build") {
             
            steps {
                script {
                    gv.buildApp()
                }
            }
                
               script{

                   gv.buildApp()
               }
           }
        }
        stage("test") {
            when {
                expression {
                    params.executeTests
                }
          when{
               expression {
                 params.executedTests
               }
            }
            steps {
                script {
                    gv.testApp()
                }
                
                 script{

                   gv.testApp()
               }
            }
        }
        stage("deploy") {
             
            
            steps {
                script {
                    gv.deployApp()
                }
                
                script{

                   gv.deployApp()
               }
            }
        }
    }   
}
