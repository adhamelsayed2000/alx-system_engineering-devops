# Task 2

----
## 2. Secured and monitored web infrastructure
On a whiteboard, design a three server web infrastructure that hosts the website `www.foobar.com`, it must be secured, serve encrypted traffic, and be monitored.

Requirements:

	* You must add:
		* 3 firewalls
		* 1 SSL certificate to serve www.foobar.com over HTTPS
		* 3 monitoring clients (data collector for Sumologic or other monitoring services)
	* You must be able to explain some specifics about this infrastructure:
		* For every additional element, why you are adding it
		* What are firewalls for
		* Why is the traffic served over HTTPS
		* What monitoring is used for
		* How the monitoring tool is collecting data
		* Explain what to do if you want to monitor your web server QPS
	* You must be able to explain what the issues are with this infrastructure:
		* Why terminating SSL at the load balancer level is an issue
		* Why having only one MySQL server capable of accepting writes is an issue
		* Why having servers with all the same components (database, web server and application server) might be a problem

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

-----
## Explanation
    For every additional element, why you are adding it:
        Load Balancer: Added to distribute incoming traffic among multiple servers for improved performance, scalability, and redundancy.
        Firewall: Added for security to control incoming and outgoing traffic and prevent unauthorized access or malicious attacks.
        HTTPS (SSL/TLS): Implemented to encrypt communication between clients and servers for data privacy and security.
        Monitoring: Added to monitor the health, performance, and availability of the infrastructure and detect and resolve issues proactively.

    What are firewalls for:
        Firewalls are network security devices that monitor and control incoming and outgoing network traffic based on predetermined security rules.
        They are used to establish a barrier between a trusted internal network and untrusted external networks (like the internet) to prevent unauthorized access, malicious attacks, and data breaches.

    Why is the traffic served over HTTPS:
        HTTPS encrypts communication between clients (e.g., web browsers) and servers, ensuring that data transmitted over the network is encrypted and secure.
        It protects sensitive information such as login credentials, personal data, and financial information from eavesdropping, tampering, and man-in-the-middle attacks.

    What monitoring is used for:
        Monitoring is used to continuously observe and analyze the health, performance, and availability of the infrastructure and its components.
        It helps detect and diagnose issues, predict potential failures, optimize performance, and ensure the reliability and stability of the system.

    How the monitoring tool is collecting data:
        The monitoring tool collects data by periodically querying various metrics and parameters from the monitored components such as servers, network devices, databases, and applications.
        It may use protocols like SNMP, HTTP, or custom APIs to gather performance metrics, logs, event data, and other relevant information from the monitored systems.

    Explain what to do if you want to monitor your web server QPS:
        To monitor the web server's QPS (Queries Per Second), you can configure the monitoring tool to collect metrics related to web server performance, such as request count, response time, and throughput.
        This can be done by setting up monitoring agents on the web server or using built-in monitoring capabilities of the web server software (e.g., Apache, Nginx).
        The monitoring tool can then aggregate and display QPS metrics over time, allowing you to track the server's workload and performance.
-----
## Problems/Issues
    Why terminating SSL at the load balancer level is an issue:
        Terminating SSL at the load balancer means decrypting encrypted traffic before forwarding it to backend servers.
        This can expose sensitive data (such as user credentials) in transit between the load balancer and backend servers, potentially compromising data security.

    Why having only one MySQL server capable of accepting writes is an issue:
        Having a single MySQL server for write operations creates a single point of failure (SPOF) for data writes.
        If the MySQL server fails, write operations will be disrupted, leading to data inconsistency and potential loss of data.

    Why having servers with all the same components (database, web server, and application server) might be a problem:
        Having servers with identical components increases the risk of widespread failures or issues affecting all servers simultaneously.
        It lacks redundancy and fault tolerance, making the infrastructure more vulnerable to outages, performance degradation, and data loss.