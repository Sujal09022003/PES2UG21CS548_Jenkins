pipeline{
    agent any 
        stages{
              stage('clone repository'){
                steps{
                    checkout([$class:'GitSCM',
                    branches:[[name:'*/main']],
                    userRemoteConfigs: [[url:'https://github.com/Sujal09022003/PES2UG21CS548_Jenkins.git']]])
                }
              }
              stage('Build'){
                steps{
                    build 'PES2UG21CS548-1'
                    sh 'g++ jenkins.cpp -o output'
                    echo 'Build Stage Successful'
                }
              }
              stage('Test'){
                steps{
                    sh './output'
                    echo 'test stage successfully'
                }
              }
              stage('Deploy'){
                steps{
                    echo 'deployment successfull'
                }
              }
        }
        post{
            failure{
                echo 'pipeline failed'
            }
        }
    }
