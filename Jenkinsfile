pipeline {
	   agent any
	   stages {
	      stage ('Run jmeter scripts') {
	          steps {
	           sh' rm $WORKSPACE/pipelinejmeter/*.jtl '
    
                //sh' mkdir $WORKSPACE/pipelinejmeter/result '
                sh'  cd "$WORKSPACE/pipelinejmeter" '
                   
                sh ' /usr/local/bin/jmeter -n -t MVP1.0MaxLTV.v2.jmx -l $WORKSPACE/pipelinejmeter/jmeter.jtl  '
		//sh ' /usr/local/bin/jmeter -n -t MVP1.0MaxLTV.v2.jmx -l /usr/local/bin/jmeter.jtl  ' 
                   
                }

	        }
	     stage ('publish report') {
		  steps {
			  perfReport compareBuildPrevious: true, excludeResponseTime: true, modePerformancePerTestCase: true, modeThroughput: true, sourceDataFiles: '/usr/local/bin/*.jtl'
	    
		        }		   
		    }
	      
		   
	 }
		   
	   
}
