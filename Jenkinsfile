pipeline {
    agent {
        docker{
            image "ruby:alpine"
        }
    }
    stages{
    stage("Build"){
        steps{
           sh 'mvn clean install'
        cucumber failedFeaturesNumber: -1, failedScenariosNumber: -1, failedStepsNumber: -1, fileIncludePattern: 'target/*.json', pendingStepsNumber: -1, skippedStepsNumber: -1, sortingMethod: 'ALPHABETICAL', undefinedStepsNumber: -1                       
    }
            sh "chmod +x build/alpine.sh"
            sh "./build/alpine.sh"
            sh "bundle install"
        }
    }

    stage("Tests"){
        steps{
            sh "bundle exec cucumber -p ci"
        }
      }
    }
}