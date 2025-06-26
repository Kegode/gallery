pipeline{
    agent any

    environment{
        SLACK_URL = credentials('SLACK_URL')
        RENDERED_URL = 'https://gallery-45jb.onrender.com/'
    }
    
   
    stages{
        stage('cloning'){
            steps
            {
                git branch: 'master', url: 'https://github.com/Kegode/gallery.git'
            }
            }

        stage('prepare project'){
                steps
            {
                sh 'npm install'
            }
            }
        stage('tests'){
                steps
            {
                sh 'npm test'
            }
            }

        stage('Deploy'){
                steps
            {
                sh 'curl -X POST https://api.render.com/deploy/srv-d1at5r8dl3ps73e2mcsg?key=7h0NW4Ddv6Q'
            }
            }
        
    }
    post{
        success {
                echo 'App has been deployed and now you can access it using the link below:'
                sh """
                    curl -X POST -H 'Content-type: application/json' \\
                     --data '{
                    "text": "*App has been deployed and now you can access it using the link below:*\n#${env.BUILD_NUMBER} succeeded!\n<${env.RENDERED_URL}|View App>"
                }' \\
                $SLACK_URL
                """
                }

    }
}