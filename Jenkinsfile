pipeline{
	agent any
	tools{
		maven 'Maven'
	}
	stages{
	stage('Checkout'){
	steps{
		git branch:'master', url:'https://github.com/bindushreebd/maventest.git'
		}
	}
	stage('Build'){
	steps{
		sh 'mvn clean package'
		}
	}
	stage('Test'){
	steps{
		sh 'mvn test'
		}
	}
	stage('Run Application'){
	steps{
		sh 'java -jar target/maventest-1.0-SNAPSHOT.jar'
		}
	}
	}
	post{
	success{
		echo 'Build and deployment'
		}
	failure{
		echo 'build failure'
		}
	}
}
