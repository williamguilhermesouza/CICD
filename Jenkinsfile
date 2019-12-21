node {
    checkout scm
    // Pega o commit id para ser usado de tag (versionamento) na imagem
    sh "git rev-parse --short HEAD > commit-id"
    tag = readFile('commit-id').replace("\n", "").replace("\r", "")
    
    // configura o nome da aplicação, o endereço do repositório e o nome da imagem com a versão
    // appName = "app"
    // registryHost = "127.0.0.1:30400/"
    // imageName = "${registryHost}${appName}:${tag}"

    stage("test") {
        sh "docker build -t app:v1 ."
    }

    stage("build") {
        sh "kubectl get nodes"
        echo "$PATH"
        //sh "kubectl run app --image nginx"
        //sh "kubectl expose deployment app --type LoadBalancer"
    }
}