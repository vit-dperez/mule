pipeline {
    agent { label 'ubuntu' }
    parameters {booleanParam(name: 'CHOICES', defaultValue: true, description: 'Choinces?')}
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
              def apiList = []
              def files = findFiles()
              files.each{ f ->
                if(f.directory){
                    choices.add(f.name)
                }
              }
	          if (params.CHOICES){
	          choices = params.CHOICES
	          }
	          echo "Selected Choices: ${choices}"
	        }
	    }
    }
  }
}

