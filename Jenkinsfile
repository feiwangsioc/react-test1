def agentLabel {
    agentLabel = "aws-linux2-1"
}

pipeline {
    agent {label agentLabel}
    environment {
        SLAVE_NODE = "${"aws-linux2-1"}"
    }
          stage("npm run build") {
        when {
            anyOf {
                branch 'develop';
                branch 'master'
            }
        }
        //build deploy image for develop and release branch only
        steps {
          sh "npm install"
          sh "npm run build"
          sh "npm start"
        }
      }
}
