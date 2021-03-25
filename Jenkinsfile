pipeline {
     agent any

     tools {nodejs "node"}

     stages {
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "rm -rf /var/www/html"
                sh "mkdir /var/www/html"
                sh "cp -r ${WORKSPACE}/build/ /var/www/html/"
            }
        }
    }
}