pipeline {
    agent any

    stages {
        stage('Hell00') {
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
         cat pom.xml
         '''
       }
     }

   }
}
