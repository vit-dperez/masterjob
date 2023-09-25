def paramsListStart= [
    choice(
        choices: ['GSPRF','GSDEV','GSTRN','GSSIT','GSUAT','GSUQA','GSPRD'], 
        name: 'env',
        description: 'Environment to Deploy'
    )
]
def paramsListEnd= [
    choice(
        choices: ['us-east-2','us-east-1'], 
        name: 'region'
    ),
    gitParameter(
        branchFilter: 'origin/(.*)', //filtering this common part of all branch names
        defaultValue: 'master', 
        name: 'BRANCH', 
        type: 'PT_BRANCH'
    )
]

properties([
    parameters(
        paramsListStart + paramsListEnd
    )
])

pipeline{
    agent { label 'ubuntu'}
    parameters {
        booleanParam(name: 'api1', defaultValue: false, description: '........')
        booleanParam(name: 'api2', defaultValue: false, description: '........')
        booleanParam(name: 'api3', defaultValue: false, description: '........')
        booleanParam(name: 'api4', defaultValue: false, description: '........')
        booleanParam(name: 'api5', defaultValue: false, description: '........')
    }
    options{buildDiscarder(logRotator(numToKeepStr: '3')) }

    stages {

        stage('Deploy api') {
            steps {
                script {
                        if (params.api1){
                            build wait: false, job: '/mule/mule-1-api', parameters: [string(name: 'env', value: "${params.env}"), string(name: 'region', value: "${params.region}"), gitParameter(name: 'BRANCH', value: "${params.BRANCH}")]}
                        }
                        if (params.api2){
                            build wait: false, job: '/mule/mule-2-api', parameters: [string(name: 'env', value: "${params.env}"), string(name: 'region', value: "${params.region}"), gitParameter(name: 'BRANCH', value: "${params.BRANCH}")]}
                        }
                        if (params.api3){
                            build wait: false, job: '/mule/mule-3-api', parameters: [string(name: 'env', value: "${params.env}"), string(name: 'region', value: "${params.region}"), gitParameter(name: 'BRANCH', value: "${params.BRANCH}")]}
                        }
                        if (params.api4){
                            build wait: false, job: '/mule/mule-4-api', parameters: [string(name: 'env', value: "${params.env}"), string(name: 'region', value: "${params.region}"), gitParameter(name: 'BRANCH', value: "${params.BRANCH}")]}
                        }
                        if (params.api5){
                            build wait: false, job: '/mule/mule-5-api', parameters: [string(name: 'env', value: "${params.env}"), string(name: 'region', value: "${params.region}"), gitParameter(name: 'BRANCH', value: "${params.BRANCH}")]}
                        }
                }
            }
        }
    }
}