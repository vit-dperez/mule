pipeline {
    agent { label 'ubuntu' }
    parameters {booleanParam(name: 'CHOICES', defaultValue: true, description: 'Toggle this value')}
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
	      if (params.CHOICES){
	      choices = params.CHOICES.split(",")
	    }
	    echo "Selected Choices: ${choices}"
	  }
	}
    }
  }
}

