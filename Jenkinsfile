node("devops-node") {
    stage("Checkout") {
        checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/mchekini-check-consulting/pro-epargne-devops.git']])
    }

    stage("deploy Devops Tools") {
        try {
            sh "sudo docker-compose down"
        } catch (Exception e) {
            println "No Containers Running"
        }
        finally {
            sh "sudo docker-compose up -d"
        }

    }
}