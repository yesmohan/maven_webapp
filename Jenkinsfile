pipeline {

       agent { label 'master' }

   	stage("Cloning frm git") {
		steps {
		 echo "am cloing frm git"                
		}

	}

	stage("Build using Maven") {
 		steps {
                 echo "am building using maven"
		}

	}

	stage("Results") {
               steps {
    		echo "this is a test stage"
		
		}
	}
}
