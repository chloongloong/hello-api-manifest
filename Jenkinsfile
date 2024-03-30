pipeline {
    //environment {
//	IMAGE_TAG = ''
 //   }
    agent any

    stages {
	stage('Cloning Repo') {
	    steps {
		git 'https://github.com/chloongloong/hello-api-manifest.git'
	    }
	}

	stage('CD - Update Manifest with new version number for the newly built image') {
		parameters {
        		string(defaultValue: '0', description: 'This is a parameter', name: 'IMAGE_TAG')
    		    }

		steps {
			script {
				sh """
				    echo ${param.IMAGE_TAG}
				    pwd
				    ls -lrt
				    cat deployment-hello-hapi.yaml
				    //sed -i 's/hello-hapi:.*/hello-hapi:'"${param.IMAGE_TAG}"'/g' deployment-hello-hapi.yaml
				    //grep hello-hapi:.* deployment-hello-hapi.yaml
				    //git config --global user.name “chloongloong”
				    //git config --global user.email "loongch@yahoo.com.sg"
				    //git add deployment-hello-hapi.yaml
				    //git commit -m "Updated deployment Manifest to image ver ${param.IMAGE_TAG}"
				   """
			       //withCredentials([gitUsernamePassword(credentialsId: 'GITHUB-PAT-USERPASS', gitToolName: 'Default')]) {
				   //sh "git push https://github.com/chloongloong/hello-api-manifest main"
			       //}
			}
		}
	}
    }
}
