pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
				sh '''#!/bin/bash
				ls -ltra'''
                echo 'Building..'
				
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}