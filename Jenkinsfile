def templateName = 'poc-acebp'
def repoUrl = "https://github.com/amvargasg/POC-aceBP.git"

pipeline {
    
  agent any
  
   /*environment {
        APP = '${templateName}'
        NAMESPACE   = '${openshift.project()}'
    }*/
   
  stages {

 /*     
    stage('preamble') {
        steps {
            script {
                openshift.withCluster() {
                    openshift.withProject() {
                        echo "Using project: ${openshift.project()}"
                    }
                }
            }
        }
    }// end of stage 'preamble' */

    stage('Checkout') {
            steps {
                sh 'echo git checkout'
                /* checkout([$class: 'GitSCM', branches: [[name: '*main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'jenkins-user-github', url: repoUrl]]])
                sh "ls -lart ./*" */
            }
    }// end of stage 'checkout'     
    
    stage('Compile - Generate Bar') {
            steps {
                sh 'echo Compile Bar'
              
            }
    }// end of stage 'Compile'

    stage('Build and Push Image') {
            steps {
                sh 'echo Build and Push Image'
                /*sh '''
                    
                    oc start-build imag-poc-ace -w
                    
                '''*/
              
            }
    }// end of stage 'Build'
    
    /*
    stage('cleanup') {
      steps {
        script {
            openshift.withCluster() {
                openshift.withProject() {
                  sh 'oc get all --selector app=poc-acebp -o name'
                  openshift.selector("all", [ app : templateName ]).delete() 
                  sh 'oc get all --selector app=poc-acebp -o name'
                  echo "Cleanup done"
                }
            }
        }
      }
    } // end of stage 'cleanup'*/
      
    /*
    stage('Deploy - Apply template') {
      steps {
        script {
            openshift.withCluster() {
                openshift.withProject() {
                    echo 'Create openshift objects from yaml file'
                    sh 'oc apply -f templateOC/template.yaml'
                    sh 'oc get all --selector app=poc-acebp -o name'
                }
            }
        }
      }
    }// end of stage 'deployment'*/
    
      
    
/*    stage('Sonar - Analisis'){
        steps{
          script{
                  echo "Sonar"
              }
            withSonarQubeEnv('sonarqube'){
              nodejs(nodeJSInstallationName: 'node') {
                    sh 'npm install' 
                    sh 'npm install sonar-scanner'
                    sh 'npm run sonar'
                }
                 
             }
        }
    }*/
  }
  
}
