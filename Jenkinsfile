node('docker') {
    def app
    stage('Clone repository') {
        checkout scm
    }
    stage('Build image') {
        app = docker.build("haoling/pandorafms-console", "pandora_console")
    }
    stage('Push image') {
        docker.withRegistry('https://drive.fei-yen.jp:5443') {
            app.push("dev-${env.BUILD_NUMBER}")
            app.push("6")
        }
    }
}
