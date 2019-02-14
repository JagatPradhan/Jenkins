pipeline{
node any
stages{
stage('git checkout'){
checkout scm
}
stage('sonar analysis'){
sh 'mvn clean verify sonar:sonar
-Dsonar.projectName=PRADHAN
-Dsonar.projectKey=PRADHAN
-Dsonar.projectVersion=$BUILD_NUMBER';
}

}

}
