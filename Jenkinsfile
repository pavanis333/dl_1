pipeline {
    
    agent {
        
        label 'deep'
        
    }

    stages {
        
        stage('model generation') {
            
            steps {
            
                git branch: 'main', url: 'https://github.com/pavanis333/dl_1.git'
                
                sh '/**/python3 pima_india_diabete.py'
                
                stash includes: 'pima_indias_diabetes_model.h5', name: 'model'
                
            }
        }
        
        stage('delivery') {
            
            steps {
                
                unstash 'model'
            }
        }
    }
}
