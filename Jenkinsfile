node {
        stage('Checkout myself, and something else') {
            checkout([
                poll: false,
                $class: 'GitSCM',
                branches: [[name: 'refs/heads/master']],
                doGenerateSubmoduleConfigurations: false,
                submoduleCfg: [],
                userRemoteConfigs: [[credentialsId: 'priority-ci-user-git-creds-id', url: "git@github.com:fatal-exception/j2-hello-world"]]
            ])
            checkout(
                poll: false,
                scm: [
                    $class: 'GitSCM',
                    branches: [[name: 'refs/heads/master']],
                    doGenerateSubmoduleConfigurations: false,
                    extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: "blah"]],
                    submoduleCfg: [],
                    userRemoteConfigs: [[credentialsId: 'priority-ci-user-git-creds-id', url: "git@github.com:fatal-exception/temp_http"]]
                ]
            )
        }
  sh 'ls'
  sh 'ls blah'
  echo "hello world"
}
