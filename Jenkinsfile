pipeline {
    agent any
    stages {
        stage('Build-Verbs') {
            steps {
		echo "Building verbs using bazel..."
		sh 'bazel build -c opt //tensorflow_networking/verbs:verbs_server_lib'
            }
        }
        stage('Build-Gdr') {
            steps {
                echo "Building gdr using bazel..."
                sh 'bazel build -c opt //tensorflow_networking/gdr:gdr_server_lib'
            }
        }
        stage('Build-Mpi') {
            steps {
                echo "Building mpi using bazel..."
                sh 'MPI_HOME=/usr TF_NEED_MPI=1 ./configure && bazel build -c opt //tensorflow_networking/mpi:all'
            }
        }
        stage('Container-Test') {
            steps {
                echo "Building mpi using container..."
                sh 'docker build --tag="jenkins-mpi-docker" -f //tensorflow_networking/mpi/Dockerfile .'
            }
        }
    }
}



