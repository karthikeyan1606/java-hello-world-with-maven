#!/usr/bin/env groovy
def appName= 'testing'
def major_version = 1.0 


node{ 

stage('cloning repo'){
  checkout scm
}

stage('Testing')
{
sh 'ls -la'
echo "Building application ${appName} with version ${major_version}"
}


stage('Build'){
sh 'mvn clean install'
}
}
