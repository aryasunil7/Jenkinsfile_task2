node {
	try{
	stage 'Checkout' 	
		checkout scm
		
		def exists = fileExists 'file1.yml'
		if (exists) {
    			echo 'Yes'
		} else {
    			echo 'No'
		}
		stage 'Syntax check' 	
			sh 'ansible-playbook --syntax-check ./file1.yml'
		stage 'Run playbook' 	
			sh 'ansible-playbook file1.yml'
	currentBuild.result = 'SUCCESS'
	}catch (Exception err) {
        currentBuild.result = 'FAILURE'
    }
    	echo "RESULT: ${currentBuild.result}"
}
