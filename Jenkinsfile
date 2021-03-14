node {
  stage 'Building image'
  checkout scm
  def newApp = docker.build 'asantra1/springweb:v1', 'springbootwebapp'
  newApp.push() // record this snapshot (optional)
  
  stage 'Test image'
  // run some tests on it (see below), then if everything looks good:
  stage 'Approve image'
  newApp.push 'latest'
}
