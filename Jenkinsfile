pipeline {
	   agent any
	   stages {
	      stage ('Run jmeter scripts') {
	          steps {
	           // sh' rm $WORKSPACE/pipelinejmeter/*.jtl '
    
                sh' mkdir $WORKSPACE/pipelinejmeter/result '
                sh'  cd "$WORKSPACE/pipelinejmeter" '
                   
                 sh ' jmeter -n -t MVP1.0MaxLTV.v2.jmx -l $WORKSPACE/pipelinejmeter/jmeter.jtl $WORKSPACE/pipelinejmeter/result '
                   
                }

	        }
	    }
	   
	}
