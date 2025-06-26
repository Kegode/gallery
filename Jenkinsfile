pipeline{
    agent any
    tools{
        nodejs "nodejs"
    }
   
    stages{
        stage('cloning'){
            steps
            {
                git branch: 'master', url: 'https://github.com/Kegode/gallery.git'
            }
            }

        stage('set up project'){
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
}