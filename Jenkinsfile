#!/usr/bin/env groovy
def appName= 'testing'
def major_version = 1.0 
def build_number =  BUILD_NUMBER
def version =appName + '-' + major_version + '.' + build_number

node{ 

stage('cloning repo'){
  checkout scm
}

  stage('Test'){
sh 'mvn clean test'
}

stage('Build'){
echo "Building app with version ${version}"
sh 'mvn clean install'
}
  
  stage('renaming jar'){
    sh 'mv $WORKSPACE/target/jb*.jar $WORKSPACE/target/"${version}"'
    sh 'ls -la $WORKSPACE/target'
  }
  
}
