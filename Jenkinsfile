node {
    checkout scm
    def dockerfile = 'Dockerfile.dev'
    def customImage = docker.build("tanuj3107/react-test", "-f ./client/Dockerfile.dev ./client") 
    customImage.push()
}