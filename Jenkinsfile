pipeline {
    agent any
    stages {
        stage('Example Build') {
            when {
                allOf { 
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
