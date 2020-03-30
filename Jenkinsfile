pipeline {
    agent {
        docker {
            image "ruby:alpine"
            //args "--network=skynet -u root --privileged"
        }
    }
    stages {
        stage("Build") {
            steps {
                input(message: "pode  proseguir?", ok: "Sim")
                sh "chmod +x build/alpine.sh"
                sh "./build/alpine.sh"
                sh "bundle install"
            }
        }
        stage("Tests") {
            steps {
                sh "bundle exec cucumber -p ci"
            }
        }
    }
}
