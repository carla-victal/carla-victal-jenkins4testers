pipeline {
    agent any
    stages{
    stage("Build"){
        steps{
            sh "bundle install"
        }
    }

    stage("Tests"){
        steps{
            sh "echo 'simulandoum teste automatizado'"
        }
      }
    }
}