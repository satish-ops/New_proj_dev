pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
       stage('for the fix branch'){
        when{
            branch "fix-*"
        }
    steps{
        sh '''
         cat READ.md
         '''
       }
     }
        stage('for pr'){
            when{
                branch 'PR-*'
            }
            steps{
                echo 'this only runs for pr'
            }    
         }
      }
  }
