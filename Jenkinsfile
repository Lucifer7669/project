pipeline{
   agent {
    label {
        label "built-in"
        customWorkspace "/mnt/source-code/"
    }
   }

   stages {
    stage ('clone souce code') {
       steps{
        sh "sudo git clone https://github.com/Lucifer7669/project"
       }
    }

    stage ('building phase'){
        steps{
            sh "sudo cd project && mvn clean install"
        }
    }

    stage ('deployment'){
        steps{
            sh "sudo scp -i project/target/LoginWebapp.war vedant@172.31.37.41:/tmp/server/apache-tomcat-9.0.73/webapps/"
        }
    }
   }
}
