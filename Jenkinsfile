#!groovy

@Library('jenkinslib') _     

def mytools = new org.devops.tools()



pipeline {
    agent { node {  label "master" }}

    stages {
        //下载代码
        stage("GetCode"){ 
            steps{  
                timeout(time:5, unit:"MINUTES"){   
                    script{ 
                        mytools.PrintMes("获取代码",'green')
                    }
                }
            }
        }
        stage("mavenBuild"){
            steps{
                script{
                    def mvnHome = '/usr/local/apache-maven-3.6.0'
                 sh "${mvnHome}/bin/mvn  clean package "
                }
            }
        }
    }
}
