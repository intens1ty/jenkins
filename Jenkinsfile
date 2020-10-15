pipeline {
    agent any
    environment {
        BUILD="$JOB_NAME"
    }
    stages {
      stage ('Hello') {
        when {
            expression { "$BUILD" == "Stage" }
        }
          steps {
          echo "test"
      }   
    }
  }
}
