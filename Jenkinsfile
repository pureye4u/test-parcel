node {
  def hello = 'Hello jenkins'
  stage ('clone') {
    git 'https://github.com/pureye4u/test-parcel.git'
  }
  dir ('sample') {
    stage ('sample/execute') {
      sh 'chmod +x execute.sh'
      sh './execute.sh'
    }
    stage ('print') {
      print(hello)
    }
  }
  stage ('install') {
    sh 'yarn build'
  }
  stage ('build') {
    sh 'yarn install'
  }
}

void print(message) {
  echo "${message}"
}
