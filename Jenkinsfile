node {
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com/repositories') {

        docker.image('tanuj3107/react-test').inside {
            sh 'docker build -t tanuj3107/react-test -f ./client/Dockerfile.dev ./client'
        }
    }
}