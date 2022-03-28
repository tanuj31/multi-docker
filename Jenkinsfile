node {
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com/repositories', 'dockerhub') {

        def customImage = docker.build("tanuj3107/react-test")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}