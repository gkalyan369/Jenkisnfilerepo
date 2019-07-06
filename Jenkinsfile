pipeline {
    agent any
	stages {
		stage ('Code Checkout '){
			git url: 'https://github.com/snp-technologies/sample-cicd-java.git'
			}
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
			}
        stage('Test') {
            steps {
                echo 'Testing..'
            }
	}
	}
}