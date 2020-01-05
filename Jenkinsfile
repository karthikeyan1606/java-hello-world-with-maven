#!/usr/bin/env groovy
def appName= 'testing'
def major_version = 1.0 
def version =appName + '-' + major_version + '.' + env.$BUILD_NUMBER

node{ 

stage('cloning repo'){
  checkout scm
}

  stage('Test'){
sh 'mvn clean test'
}

stage('Build'){
sh 'mvn clean install'
}
  
  stage('renaming jar'){
    sh 'mv $WORKSPACE/target/jb*.jar $WORKSPACE/target/${version}'
    sh 'ls -la $WORKSPACE/target'
  }
  
}
