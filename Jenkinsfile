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
}

void print(message) {
  echo "${message}"
}
