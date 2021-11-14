pipeline {

    agent any


      stages {
          stage ('pull') {
                steps {
                   script{
                       checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                           userRemoteConfigs: [[
                               credentialsId: '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',
                               url: 'https://github.com/TiffanyNgono/project-cd.git']]])

                
            }
        }

        

        
       
    }
        
        stage('Install') {
             steps{
                script{
                    sh "sudo npm install"
                }
            }
        }
        
        stage ('build') {
              steps {
                 script{
                     sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "
                   }
              }
          }
        
          
          stage ('docker') {
              steps {
                 script{
                     sh "ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml "
                   }
              }
          }
          
          
    
    
}
}
