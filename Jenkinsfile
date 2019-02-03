pipeline {
    agent any
    stages {
        stage('Container-Verbs') {
		echo "Building verbs using container..."
		sh 'docker build --tag="jenkins-verbs-docker" -f ./tensorflow_networking/verbs/Dockerfile .'
	}
    }
    post {
        failure {
            mail to: yanivbl@mellanox.com, subject: 'The verbs build failed :('
        }
    }
}

pipeline {
    agent any
    stages {
        stage('Container-Gdr') {
                echo "Building gdr using container..."
                sh 'docker build --tag="jenkins-gdr-docker" -f ./tensorflow_networking/gdr/Dockerfile .'
        }
    }
    post {
        failure {
            mail to: yanivbl@mellanox.com, subject: 'The Pipeline failed :('
        }
    }
}

pipeline {
    agent any
    stages {
    	stage('Container-Mpi') {
                echo "Building mpi using container..."
                sh 'docker build --tag="jenkins-mpi-docker" -f ./tensorflow_networking/mpi/Dockerfile .'
    	}
    }
    post {
        failure {
            mail to: yanivbl@mellanox.com, subject: 'The Pipeline failed :('
        }
    }

}




