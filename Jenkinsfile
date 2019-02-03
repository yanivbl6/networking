pipeline {
    agent any

    stages {
        stage('Build-Verbs') {
            steps {
		echo "Building verbs using bazel..."
		sh 'bazel build -c opt //tensorflow_networking/verbs:verbs_server_lib'
            }
        }
    }
}
