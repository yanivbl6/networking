pipeline {
    agent any
    stages {
        stage('Container-Verbs') {
            steps{
		echo "Building verbs using container..."
		sh 'docker build --tag="jenkins-verbs-docker" -f ./tensorflow_networking/verbs/Dockerfile .'
	    }
	}
    }
}

pipeline {
    agent any
    stages {
        stage('Container-Gdr') {
            steps{
                echo "Building gdr using container..."
                sh 'docker build --tag="jenkins-gdr-docker" -f ./tensorflow_networking/gdr/Dockerfile .'
	    }
        }
    }
}

pipeline {
    agent any
    stages {
    	stage('Container-Mpi') {
	    steps{
                echo "Building mpi using container..."
                sh 'docker build --tag="jenkins-mpi-docker" -f ./tensorflow_networking/mpi/Dockerfile .'
	    }
    	}
    }
}




