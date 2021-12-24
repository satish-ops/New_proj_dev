      pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building the .NETCore applcaion'
          }
        }

        stage('only for PR') {
              when {
                   branch 'PR-*'
              }
          steps {
            echo 'Testing the application'
            echo "Get the DriverPath ${ChromeDriverPath}"
          }
        }

        stage('Test Log') {
          environment {
            LocalVariable = 'HelloLocal'
          }
          steps {
            writeFile(file: 'LogTestFile.txt', text: "This is the right ChromeDriverPath ${ChromeDriverPath} and localvariable Value ${LocalVariable}")
          }
        }

      }
    }

    stage('Deploy only for fix') {
      when {
        branch 'fix-123'
      }
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploying the app in IIS server'
          }
        }

        stage('Artifacts') {
          steps {
            echo 'LogTestFile.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Driver\\Path\\ChromeDriver.exe'
  }
}
