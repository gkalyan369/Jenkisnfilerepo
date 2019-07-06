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
               bat 'mvn clean verify versions:set -DnewVersion=1.0.0'
			   bat ''
            }
			}
        stage('Code Quality') {
            steps {
                echo 'Checking Code Quality'
                withSonarQubeEnv('Sonar') {
                    bat 'mvn sonar:sonar -Dsonar.login=admin -Dsonar.password=admin'
                }
            }
	}
	}
}