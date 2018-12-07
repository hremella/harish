 pipeline {
agent any 
stages {


stage('Docker Build') {

steps {

sh """ docker build -t hremella/apache . """

}
}
stage('Push to DIR'){
steps{
withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'harish',
usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]) {

sh """
docker login --username $USERNAME --password $PASSWORD
docker push hremella/apache
""" 
}
} 
}
}
}

