node{
stage('build'){
    def dockerfile = 'Dockerfile.dev'
    def customImage = docker.build("tanuj3107/react-test", "-f ./client/Dockerfile.dev ./client") 
}
stage('buildclient'){

    def clientImage = docker.build("tanuj3107/multi-client", "./client") 

   
    clientImage.push()
}
stage('buildworker'){

    def workerImage = docker.build("tanuj3107/multi-worker", "./worker") 

   
    workerImage.push()
}
stage('buildserver') {

    def serverImage = docker.build("tanuj3107/multi-server", "./server") 

   
    serverImage.push()
}
stage('buildnginx'){

    def nginxImage = docker.build("tanuj3107/multi-nginx", "./nginx") 

    nginxImage.push()
}
}