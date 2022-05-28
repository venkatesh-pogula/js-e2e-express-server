pipeline{
    agent{label ('node_nodejs')}
    stages('scm'){
        stage{
            steps{
                git 'https://github.com/venkatesh-pogula/js-e2e-express-server.git'
            }
            stage('build'){
                 sh '''npm install
                       npm run build
                       npm pack'''
            }
        }
        post{
            success{
                junit '**/TEST-.xml'
            }
        }
    }
}


