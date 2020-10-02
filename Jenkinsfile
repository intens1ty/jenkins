pipeline {
    agent any
    environment {
        BUILD="$JOB_NAME"
    }
    stages {
      stage ('Hello') {
        when {
            expression { "$BUILD" == "test2" }
        }
          steps {
          echo "test"
      }   
    }
  }
}
