pipeline {
  agent any
  environment {
    GIT_REPO = 'm3-web'
    GIT_BRANCH = 'jenkins'
    WRITERSIDE_BUILD = '233.14389'
    WRITERSIDE_APP = 'Writerside/user-guides'
    WRITERSIDE_MODULE = 'USER-GUIDES2'
    WEB_FOLDER = '/var/www/docu/m3-web'
  }
  stages {
    stage('Run Docker Container') {
      steps {
        script {
            sh '''
docker run --rm -v /var/lib/jenkins/workspace/${GIT_REPO}_${GIT_BRANCH}:/github/workspace registry.jetbrains.team/p/writerside/builder/writerside-builder:${WRITERSIDE_BUILD} /bin/bash -c '
export DISPLAY=:99
Xvfb :99 &
/opt/builder/bin/idea.sh helpbuilderinspect -source-dir /github/workspace/ -product Writerside/user-guides --runner github -output-dir /github/workspace/artifacts/ || true
echo "Test existing artifacts"
test -e /github/workspace/artifacts/webHelpUSER-GUIDES2-all.zip && echo webHelpUSER-GUIDES2-all.zip exists
if [ -z "$(ls -A /github/workspace/artifacts/ 2>/dev/null)" ]; then
  echo "Artifacts not found" && false
else
  chmod 777 /github/workspace/artifacts/
  ls -la /github/workspace/artifacts/
fi
'
'''

        }
      }
    }

    stage('Move Artifacts') {
      steps {
        script {
          sh "rm -rf ${WEB_FOLDER}"
          sh "mkdir -p ${WEB_FOLDER}"
          sh "unzip -o /var/lib/jenkins/workspace/${GIT_REPO}_${GIT_BRANCH}/artifacts/webHelp${WRITERSIDE_MODULE}-all.zip -d ${WEB_FOLDER}"
        }

      }
    }

  }

  post {
      always {
          discordSend enableArtifactsList: true, showChangeset: true, link: 'http://192.168.1.107/roadplus-api/acl.html', title: 'Roadplus API Document', webhookURL: env.DISCORD_WEBHOOK, result: currentBuild.currentResult
      }
  }
}