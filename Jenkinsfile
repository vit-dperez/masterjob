pipeline{
    agent { label 'ubuntu'}
    parameters {
        booleanParam(name: 'api1', defaultValue: false, description: '........')
        booleanParam(name: 'api2', defaultValue: false, description: '........')
        booleanParam(name: 'api3', defaultValue: false, description: '........')
    }
    options{buildDiscarder(logRotator(numToKeepStr: '3')) }

    stages {

        stage('Deploy api') {
            steps {
                script {
                        if (params.api1){
                            build wait: false, job: '/mule/mule-1-api'
                        }
                        if (params.api2){
                            build wait: false, job: '/mule/mule-2-api'
                        }
                        if (params.api3){
                            build wait: false, job: '/mule/mule-3-api'
                        }
                }
            }
        }
    }
}