pipeline {
  agent any
  
  stages {
    stage('clone') {
      steps {
        echo "cloning typescript project"
        git branch: 'main' , url: 'https://github.com/praveenkumar57/TypeScript.git'
        sh '''
          pwd
          ls -lrt
        '''
      }
    }
    
    stage('build') {
      steps {
        echo "build start"
        sh '''
          cd TypeScript
          npm install
          npm run build
          ls -la
         '''
      }
    }
  } 
}
  
        
