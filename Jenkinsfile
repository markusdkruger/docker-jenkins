node {
    def app

    stage('Clone repository') {

        checkout scm
    }

    stage('Build image') {

        app = docker.build("registry.krugercorp.co.za/jenkins")
    }

    stage('Test image') {
        
    }

    stage('Push image') {
        docker.withRegistry('https://registry.krugercorp.co.za') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
