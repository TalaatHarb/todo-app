def nodeInstallation = 'NodeJS'

timestamps {
    node () {
        stage ('Checkout') {
          checkout([$class: 'GitSCM', branches: [[name: '**']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '', url: 'https://github.com/TalaatHarb/todo-app']]]) 
        } // stage ('Checkout')

        stage('check-setup'){
            env.NODEJS_HOME = "${tool nodeInstallation}"
    	    // on linux / mac
    	    env.PATH="${env.NODEJS_HOME}/bin:${env.PATH}"
            sh 'npm --version'
        } // stage('check-setup')
        
        stage ('install') {
        
        sh """ 
         npm install
        """ 
        } // stage('install')
        
        stage ('build') {
        
        sh """ 
         npm run build 
        """ 
        } // stage('test')

        stage ('test') {
        
        sh """ 
         npm run test 
        """ 
        } // stage('test')
    } // node
} // timestamps
