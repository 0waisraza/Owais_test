flag=true
pipeline {
agent any
  parameters{
    string(name: 'VERSION',defaultvalue:'',description:'version to deploy on prod')
    choice(name: 'VERSION',choices:['1.1.0','1.2.0','1.3.0'],description:'')
    booleanParam(name:'executeTests',defaultValue: true,description:'')
  }
  environment{
    NEW_VERSION = '1.3.0'
  }
stages {
stage('Build') {
steps {
 
echo 'Building..'
 
}
}
stage('Test') {
  when{
    expression{
      params.executeTests
    }
  }
steps {
echo 'Testing..'
// Here you can define commands for your tests
}
}
stage('Deploy') {
steps {
echo 'Deploying....'
// Here you can define commands for your deployment
}
}
  }
  post{
    //The condition here will be executed
    always{
      echo'Post build condition running....'
    }
    failure{
      echo'Post Action if Build Fail'
    }
  }
}
