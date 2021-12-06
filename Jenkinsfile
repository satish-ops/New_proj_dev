pipeline {
    agent any
    stages {
        stage('Example Build') {
            when {
		anyof
		    {
                allOf { 
			branch 'PR-*'
			expression { choice =='2'}
		}
			branch 'master'; branch 'staging' 
		}
            }
            steps {
                echo 'Hello World'
            }
        }
        stage('Example Deploy') {
            when {
                branch 'production'
            }
            steps {
                echo 'Deploying'
            }
        }
    }
}
