pipeline {
    agent { label 'ubuntu' }
    environment {
      API_LIST = ''
    }
    stages {
        stage('Get Repo') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/vit-dperez/mule.git'
            }

        }
	stage('Get parameters'){
	  steps {
            script{
              def apiList = []
	      def files = findFiles()
	      files.each{ f ->
		if(f.directory){
		  apiList.add(f.name)
		  }
	      }
	      env.API_LIST = apiList
	      echo "${apiList}"
	    }
	  }
	}
    }
}

