# aerogear-security POC

This is a **proof-of-concept** (be kind) on having a very simple security controller built on top of aerogear-controller

### credits / attribution

Has some code/ideas extracted from seam-security, DeltaSpike & TorqueBox.

## References 

* https://cwiki.apache.org/confluence/display/DeltaSpike/Security+Module+Drafts (part 3/4)

# Usage

1. Download aerogear-controller-demo
	
        git clone https://github.com/aerogear/aerogear-controller-demo.git
	
2. Deploy aerogear-controller demo

        cd aerogear-controller-demo && mvn clean package
	
	    cp target/aerogear-controller-demo.war $JBOSS_HOME/standalone/deployments/
	
3. Start JBoss
	
	    $JBOSS_HOME/bin/standalone.sh
	
4. Test it!
	
	Just open your browser at http://localhost:8080/aerogear-controller-demo/login
	
	**Enter the username**: John password: Doe
	Yay, you're authenticated!
	
	Now try to close your browser and access: 
	
	    http://localhost:8080/aerogear-controller-demo/login
	
# What's missing?

* Better exception handling
* Unauthorized access Page redirection instead of disgusting HTTP 500
* User/Password cryptography definition
* Session timeout definition
* Prevent weak passwords
* Prevent brute force attack, must add a definite login attempts per unit of time and all the repeated login attempts that were failed should be logged
* Users should be required to change their password periodically