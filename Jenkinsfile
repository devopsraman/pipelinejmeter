pipeline {
	   agent any
	   stages {
	      stage ('Run jmeter scripts') {
	          steps {
	            sh' rm $WORKSPACE/*.jtl '
    
                sh' mkdir $WORKSPACE/jmeter/result '
                sh'  cd "$WORKSPACE/jmeter" '
                   
                 sh ' jmeter -n -t MVP1.0MaxLTV.v2.jmx -l $WORKSPACE/jmeter.jtl $WORKSPACE/jmeter/result '
                   
                }

	        }
	    }
	   
	}
