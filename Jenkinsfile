pipeline {
    agent any
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    stages {
        stage('Build & Publish') {
//             when { branch 'master'}
            steps {
                checkout([
                  $class: 'GitSCM',
                  doGenerateSubmoduleConfigurations: false,
                  branches: [ [name: '*/*'] ]
                ])
                script {
                    if (env.TAG_NAME) {
                        def environment_tag = 'pro'
                    } else {
                        def environment_tag = 'pre'
                    }
                    echo "We are on $BRANCH_NAME"
                    echo "And the full env is: ${env}"
                }
            }
        }

    }
}
