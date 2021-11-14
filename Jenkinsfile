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
          
          
    
    
}
}
