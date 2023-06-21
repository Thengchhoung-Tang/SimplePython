pipeline {
    
    agent any
    
    environment {
        imageName = "myphpapp"
        registryCredentials = "nexus"
        registry = "139-162-30-76.ip.linodeusercontent.com:8085"
        dockerImage = ''
    }
    
    stages {
        stage('Code checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '', url: 'https://github.com/Thengchhoung-Tang/SimplePython.git']]])                   
            }
        }
        
        stage('Building image') {
            steps{
                script {
                  dockerImage = docker.build imageName
                }
            }
        }
         // Uploading Docker images into Nexus Registry
        // stage('Uploading to Nexus') {
        //     steps{  
        //         script {
        //                 docker.withRegistry( 'http://'+registry, registryCredentials ) {
        //                 dockerImage.push('latest')
        //             }
        //         }
        //     }
        // }
        // stage('stop previous containers') {
        //     steps {
        //         sh 'docker ps -f name=myphpcontainer -q | xargs --no-run-if-empty docker container stop'
        //         sh 'docker container ls -a -fname=myphpcontainer -q | xargs -r docker container rm'
        //     }
        // }
        
        // stage('Docker Run') {
        //     steps {
        //         script {
        //             sh 'docker run -d -p 80:80 --rm --name myphpcontainer ${registry}/${imageName}:latest'
        //         }
        //     }
        // }   
    
    }
}