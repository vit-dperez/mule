pipeline {
    agent { label 'ubuntu' }
    stages {
        stage('Get Repo') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/vit-dperez/mule.git'
            }

        }
	stage('Get parameters'){
	  environment{
	    API_LIST = ''
	  }
	  steps {
            script{
              def apiList = []
	      def files = findFiles()

	      files.each{ f ->
		if(f.directory){
		  apiList.add(f.name)
		  }
	      }

	      env.API_LIST = apiList.toString()
	      echo "${env.API_LIST}"
	    }
	  }
	}
    }
}

