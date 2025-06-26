pipeline{
    agent any
    tools{
        nodejs "nodejs"
    }
    environment{

    }
    stages{
        stage{
            steps('cloning')
            {
                git branch: 'master', url: 'https://github.com/Kegode/gallery.git'
            }
            }

            stage{
                steps('set up project')
            {
                sh 'npm install'
            }
            }

            stage{
                steps('Deploy')
            {
                sh 'curl -X POST https://api.render.com/deploy/srv-d1at5r8dl3ps73e2mcsg?key=7h0NW4Ddv6Q'
            }
            }
        
    }
}