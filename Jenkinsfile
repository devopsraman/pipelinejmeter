pipeline {
	   agent any
	   stages {
	      stage ('Run jmeter scripts') {
	          steps {
	           // sh' rm $WORKSPACE/pipelinejmeter/*.jtl '
    
                //sh' mkdir $WORKSPACE/pipelinejmeter/result '
                //sh'  cd "$WORKSPACE/pipelinejmeter" '
                   
                // sh ' /usr/local/bin/jmeter -n -t MVP1.0MaxLTV.v2.jmx -l $WORKSPACE/pipelinejmeter/jmeter.jtl  '
		sh ' /usr/local/bin/jmeter -n -t MVP1.0MaxLTV.v2.jmx -l /usr/local/bin/jmeter.jtl  ' 
                   
                }

	        }
	    // stage ('publish report') {
		//   steps {
		//	  perfReport compareBuildPrevious: true, excludeResponseTime: true, modePerformancePerTestCase: true, modeThroughput: true, sourceDataFiles: '/usr/local/bin/*.jtl'
	    
		  //      }		   
		   // }
	      
		   stage ('build jmeter container') {
			  steps {
				  //sh ' /usr/local/bin/docker pull lazzurs/jmeter '
				  //sh '/usr/local/bin/docker ps'
				  
				 //sh' /usr/local/bin/docker run -dit -v /tmp:/tmp -p 1000:1000 --name master lazzurs/jmeter /bin/bash '
				 sh '/usr/local/bin/docker exec -t master /bin/bash -c "jmeter -n -t /tmp/MVP1.0MaxLTV.v2.jmx -l /tmp/jmeter1.jtl"'
				  perfReport compareBuildPrevious: true, excludeResponseTime: true, modePerformancePerTestCase: true, modeThroughput: true, sourceDataFiles: '/tmp/*.jtl'

			  }
		}
		   
		   
	 }
		   
	   
}
