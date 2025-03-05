node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/henryk92/web-count.git'
    }

    stage('Build image') {
       dockerImage = docker.build("henryk92/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
