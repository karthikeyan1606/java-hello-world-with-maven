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
echo "Building app with Name ${appName}"
sh 'mvn clean install'
}
  
  stage('renaming jar'){
    def build_number =  BUILD_NUMBER
    def appVersion = major_version + build_number
    sh 'mv $WORKSPACE/target/jb*.jar $WORKSPACE/target/"${version}".jar'
    echo "The current application name is {appName}.${appVersion}.jar"
    sh 'ls -la target/'
  }
  
}
