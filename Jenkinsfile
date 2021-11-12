pipeline {

    agent any


    stages {
       stage ('GIT') {
               steps{
                 script{
                     checkout([$class: 'GitSCM', branches: [[name: '*/main']],userRemoteConfigs: [[ credentialsId: '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',url :'https://github.com/BouzayenMohamed/CD.git']]])                 
                 }

		}
        }
        stage ('Build') {
               steps{
                 script{
                    sh "ansible/ansible-playbook build.yml -i ansible/inventory/host.yml -u root --private-key=/var/lib/jenkins/.ssh/id_rsa"
                 }
               }

        }


   }
}


