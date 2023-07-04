pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                script {
                    deployToAppService('test')
                }
            }
        }

        stage('Stage') {
            steps {
                script {
                    deployToAppService('stage')
                }
            }
        }

        stage('Prod') {
            steps {
                script {
                    deployToAppService('prod')
                }
            }
        }
    }
}

def deployToAppService(env) {
    def appName = "sree"
    def resourceGroup = "azure2121_group"
    def servicePlan = "sampleweb42 (F1: 1)"
    def appServiceName = appName + "azure2121" + env

    withCredentials([azureServicePrincipal(credentialsId: 'sree@saikrishnagorijavoluoutlook.onmicrosoft.com', subscriptionId: 'bbf868c8-d7d0-4b4b-91a3-7d2dceb38bb8')]) {
        sh "az login --service-principal --username \746ce4d8-b8ff-4313-ade0-bf5790adb8e3 --password \dd0cf686-95b3-4525-835a-d1c4b095e2cc --tenant \db41ed96-0ae4-49e3-be3b-74fe16e973cd"
        sh "git clone https://github.com/sreenivas1210/sample.git"
