pipeline{
    agent{label ('node_js_11')}
    triggers{
        cron('H * * * *')
    }
    stages{
        stage('scm'){
            steps{
                git branch: 'main' , url:'https://github.com/venkatesh-pogula/js-e2e-express-server.git'
            }
         }
        stage('build'){
            steps{
                sh '''npm install
                      npm run build
                      npm pack'''
                }
            }
        }
    post{
        success{
            archive '**/*.tgz'
        }
    }
}


