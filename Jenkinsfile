node{
stage('build'){
    checkout scm
    def dockerfile = 'Dockerfile.dev'
    def customImage = docker.build("tanuj3107/react-test", "-f ./client/Dockerfile.dev ./client") 
}
stage('buildclient'){
    checkout scm
    def clientImage = docker.build("tanuj3107/multi-client", "./client") 

    clientImage.inside {
        sh 'make test'
    }
    clientImage.push()
}
stage('buildworker'){
    checkout scm
    def workerImage = docker.build("tanuj3107/multi-worker", "./worker") 

    workerImage.inside {
        sh 'make test'
    }
    workerImage.push()
}
stage('buildserver') {
    checkout scm
    def serverImage = docker.build("tanuj3107/multi-server", "./server") 

    serverImage.inside {
        sh 'make test'
    }
    serverImage.push()
}
stage('buildnginx'){
    checkout scm
    def nginxImage = docker.build("tanuj3107/multi-nginx", "./nginx") 

    nginxImage.inside {
        sh 'make test'
    }
    nginxImage.push()
}