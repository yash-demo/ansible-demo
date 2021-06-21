pipeline {
   agent any

   stages {
     
      stage('Preparation') {
         steps {
            cleanWs()
            git 'https://github.com/yash-demo/ansible-demo.git'
         }
      }

      stage('Run ansible'){

         agent{
              docker {
                 image 'ansible_main_ansible'
                 reuseNode true
              }
         }
          steps{
                sh 'ansible-galaxy collection install community.kubernetes'
                sh 'ansible-playbook demo.yaml'
             
              
          }    
      } 
      
    }
}
