# Task 3

-----
## 3. Scale up
Readme
	* [Application server vs web server](https://intranet.alxswe.com/rltoken/toFi_SdFHyi2MaELB8ekqw)

Requirements:

	* You must add:
		* 1 server
		* 1 load-balancer (HAproxy) configured as cluster with the other one
		* Split components (web server, application server, database) with their own server
	* You must be able to explain some specifics about this infrastructure:
		* For every additional element, why you are adding it

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

-----
## Explanation
1. **For every additional element, why are adding it:**    
     Load Balancer:
        Why add it: The load balancer is added to distribute incoming traffic among multiple servers, improving performance, scalability, and fault tolerance. It ensures that no single server becomes overwhelmed with requests, thereby enhancing the overall reliability and availability of the system.

    Firewall:
        Why add it: A firewall is added for security purposes. It acts as a barrier between the internal network and external networks (such as the internet), controlling incoming and outgoing traffic based on predetermined security rules. By filtering and monitoring network traffic, the firewall helps prevent unauthorized access, malicious attacks, and data breaches.

    HTTPS (SSL/TLS):
        Why add it: HTTPS is implemented to encrypt communication between clients (such as web browsers) and servers. This encryption ensures that data transmitted over the network is secure and protected from eavesdropping, tampering, and interception by unauthorized parties. It enhances the confidentiality and integrity of sensitive information exchanged between users and the website.

    Monitoring:
        Why add it: Monitoring is crucial for overseeing the health, performance, and availability of the infrastructure components. It allows for proactive detection and resolution of issues, optimizing system performance, and ensuring uninterrupted service delivery. By monitoring various metrics and parameters, such as server load, resource utilization, and response times, administrators can identify potential problems and take corrective actions before they escalate into major issues.