node {

    stage('Checkout'){
       git_commit_details = checkout scm
       REPO_BRANCH = git_commit_details.GIT_BRANCH
       GIT_URL = git_commit_details.GIT_URL
       REPO_NAME = GIT_URL.substring(GIT_URL.lastIndexOf('/') + 1, GIT_URL.length())

       NAME_Placeholder = 'spring-boot'
       VERSION_Placeholder = 'testversion'
    }

    stage('Maven build') {
       sh "mvn compile"
    }
    
    stage('Pull Jar') {
        sh "curl --silent -O https://sig-repo.synopsys.com/bds-integrations-release/com/synopsys/integration/synopsys-detect/6.6.0/synopsys-detect-6.6.0.jar"
        sh "chmod +x synopsys-detect-6.6.0.jar"
    }

}
