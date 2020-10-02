pipeline {
    agent any
    environment {
        BUILD="$JOB_NAME"
    }
    stages {
      stage ('Hello') {
        when {
            expression { \"$BUILD\" == \"test1\" }
        }
          steps {
          echo "test"
      }   
    }
  }
}
