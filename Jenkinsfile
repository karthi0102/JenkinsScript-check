pipeline{
    agent{
        docker{
            image 'ubuntu:20.04'
        }
    }

    stages{
        stage('step1'){
            steps{
                script{
                    
                    def status = sh(script: './one.sh', returnStatus: true)
                    if(status == 0){
                        echo "exiting"
                        return
                    }
                    echo "HIII"
                }
            }
        }
        stage('step2'){
            steps{
                script{
                    sh '''
                        ./two.sh
                    '''
                }
            }
        }
    }
}