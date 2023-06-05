    pipeline {
        agent any

        tools {
            // Install the Maven version configured as "M3" and add it to the path.
            maven "Maven"
        }

        stages{
                stage('Clone SCM') {
                    steps {
                        git branch: 'main', credentialsId: 'ce974fa1-13fe-4145-8212-5452dce5b6f4', url: 'https://github.com/Lavakumarollipi/WebApp.git'
                        }
                    }
                stage('SonarScanner') {
                    steps {
                        withSonarQubeEnv('Sonarqube-9.6.1'){
                        sh "mvn sonar:sonar"
                        }
                    }
                }
               
            }
        }
