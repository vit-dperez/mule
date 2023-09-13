pipeline {
    agent { label 'ubuntu' }
    parameters {
      booleanParam(name: 'CHOICE_LIST', defaultValue='', description: 'Select multiple choices from the list')
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
              def choices = []
	      if (params.CHOICE_LIST){
	      choices = params.CHOICE_LIST.split(",")
	    }
	    echo "Selected Choices: ${choices}"
	  }
	}
    }
  }
}

