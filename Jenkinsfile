pipeline{
     agent { label 'ubuntu'}
    parameters {
        booleanParam(name: 'api1', defaultValue: false, description: '........')
        booleanParam(name: 'api2', defaultValue: false, description: '........')
        booleanParam(name: 'api3', defaultValue: false, description: '........')
    }

    stages {

        stage('Deploy api') {
            steps {
                script {
                        if (params.api1){
                            build wait: false, job: 'mule/mule-1-api'
                        }
                        if (params.api2){
                            echo "run api2 job"
                        }
                        if (params.api3){
                            echo "run api3 job"
                        }
                }
            }
        }
    }
}