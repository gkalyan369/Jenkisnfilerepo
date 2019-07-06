pipeline {
    agent any
	stages {
		stage ('Code Checkout ') {
		steps {
				checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'c9ee1891-a205-4488-acb8-343126822623', url: 'https://github.com/snp-technologies/sample-cicd-java.git']]])
			}
			}
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
			}
        stage('Test') {
            steps {
                echo 'Testing..'
            }
	}
	}
}