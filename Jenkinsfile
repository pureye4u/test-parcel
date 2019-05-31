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
    sh 'yarn install'
  }
  stage ('build') {
    sh 'yarn build'
  }
  stage ('upload') {
    withAWS(region: 'ap-northeast-2', credentials: '726a3bed-0458-4929-891c-2d7e3425add5') {
      def identity=awsIdentity();
      s3Upload(bucket: 'slowslipper.com', workingDir:'dist', includePathPattern:'**/*');
    }
  }
}

void print(message) {
  echo "${message}"
}
