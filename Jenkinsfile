#!groovy

node {
  stage ('Checkout') {
    checkout scm
  }

  stage('Check Env Parameters'){
    echo "Branch Name : ${env.GIT_BRANCH}"
    echo "Octo Server Address : ${env.octoServer}"
  }

  stage('Run Cake') {
    powershell -File build.ps1 -projectName="Jenkins_PowerShell_Cake_Tutorial" -branchName=${env.GIT_BRANCH} -octoServer=${env.octoServer} -octoApiKey=${env.octoApiKey}
  }
}
