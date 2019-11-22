
pipeline {
	    agent { label 'linux-build' }

    stages {
        stage ('Git clone sources') {
            steps {
               git url: 'https://github.com/yesmohan/maven_webapp.git'   
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn install' 
             }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
       stage ('Prepare for deployment') {
            steps {
               sh 'rm /home/ubuntu/for-deployement/a.war'
               sh 'cp target/a.war /home/ubuntu/for-deployement/'
            }
        }

       stage ('static analysis') {
            steps {
                sh 'mvn verify sonar:sonar' 
             }
           

       stage ('deploy QA') {
            steps {
                sh 'anisble-playbook deploy.yml' 
             }
        }
    }
}
