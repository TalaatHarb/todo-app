def nodeInstallation = 'NodeJS'

timestamps {
    node () {
        stage ('Checkout') {
          checkout([$class: 'GitSCM', branches: [[name: '**']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '', url: 'https://github.com/TalaatHarb/project-euler-100']]]) 
        } // stage ('Checkout')

        stage('setup'){
            env.NODEJS_HOME = "${tool nodeInstallation}"
    	    // on linux / mac
    	    env.PATH="${env.NODEJS_HOME}/bin:${env.PATH}"
            sh 'npm --version'
        } // stage('setup')

        stage ('test') {
        
        sh """ 
         npm install
         npm run test 
        """ 
        } // stage('test')
    } // node
} // timestamps
