pipeline {
    agent any

    stages {
        stage('Build') {
	    steps {
                echo 'Building..'
		sh 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
		sh 'mvn test'
            }
        }
	stage('Package') {
		steps {
		  sh 'mvn package'
		}
	}
        stage('Deploy') {
            steps {
		 sh 'curl -u admin:Password -X PUT "http://artifactory:8081/artifactory/libs-snapshot/joda-time-3523/joda-time-hibernate/1.6-SNAPSHOT/joda-time-hibernate-1.6-1-javadoc.jar" -T /var/lib/jenkins/workspace/Joda/target/joda-time-hibernate-1.6-SNAPSHOT-javadoc.jar'
	    }
        }
    }
}
