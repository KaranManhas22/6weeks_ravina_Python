pipeline{
agent any
  stages{
    stage("git clone"){
      steps{
        git url: "https://github.com/KaranManhas22/6weeks_ravina_Python.git", branch: "main"
    }
  }
    stage("build"){
      steps{
        sh 'docker build -t frontend .'
    }
  }
    stage("validation"){
      steps{
        sh 'docker stop frontend-container || true'
        sh 'docker rm frontend-container || true'
    }
  }
    stage("RUN"){
      steps{
        sh 'docker run -d --name frontend-container -p 5173:5173 frontend'
    }
  }
}
}
