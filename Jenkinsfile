@Library('my-shared-library') _

pipeline {
    agent any

    environment {
        REPO_URL = 'https://github.com/vijay8564/spring-petclinic.git'
        BRANCH = 'main'
        MAVEN_HOME = '/usr/share/maven'
        NEXUS_REPO_URL = 'http://nexus.example.com/repository/maven-releases/'
        CREDENTIALS_ID = 'nexus-credentials'
        GROUP_ID = 'com.example.projecta'
        ARTIFACT_ID = 'project-a'
        VERSION = '1.0.0'
    }

    stages {
        stage('Checkout') {
            steps {
                gitCheckout(REPO_URL, BRANCH)
            }
        }

        stage('Build') {
            steps {
                mvnBuild('clean package', MAVEN_HOME)
            }
        }
        /*
        stage('Deploy') {
            steps {
                deployToNexus(NEXUS_REPO_URL, CREDENTIALS_ID, GROUP_ID, ARTIFACT_ID, VERSION, 'jar', 'target/*.jar')
            }
        }
        */
    }
}
