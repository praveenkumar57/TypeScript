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
    
    stage('fetch tags') {
      steps {
        sh '''
          git fetch --all --tags
          git for-each-ref --sort=-creatordate | grep 'tags'| cut -f 3 -d "/" > tags.txt
          cat tags.txt
          RECENT_TAG=$(cat tags.txt | head -1)
          echo $RECENT_TAG
          '''
      }
    }
    
    stage('build') {
      steps {
        echo "build start"
        sh '''
          
          npm install
          npm run build
          ls -la
         '''
      }
    }
  } 
}
  
        
