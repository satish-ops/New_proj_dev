      stage("AllOf") {
        when {
            allOf {
                environment name:'VALUE_ONE', value: '1'
                environment name:'VALUE_TWO', value: '2'
            }
        }
        steps {
            echo "AllOf Works!!"
        }
      }
