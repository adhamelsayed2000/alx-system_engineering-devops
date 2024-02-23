# Task 1

-------
## 1. Distributed web infrastructure
On a whiteboard, design a three server web infrastructure that hosts the website `www.foobar.com`.

Requirements:

	* You must add:
		* 2 servers
		* 1 web server (Nginx)
		* 1 application server
		* 1 load-balancer (HAproxy)
		* 1 set of application files (your code base)
		* 1 database (MySQL)
	* You must be able to explain some specifics about this infrastructure:
		* For every additional element, why you are adding it
		* What distribution algorithm your load balancer is configured with and how it works
		* Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both
		* How a database Primary-Replica (Master-Slave) cluster works
		* What is the difference between the Primary node and the Replica node in regard to the application
	* You must be able to explain what the issues are with this infrastructure:
		* Where are SPOF
		* Security issues (no firewall, no HTTPS)
		* No monitoring

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

-----
## Explanation
    For every additional element, why you are adding it:
        Load Balancer: It's added to distribute incoming traffic among multiple servers to improve performance, scalability, and redundancy.
        Firewall: Added for security by controlling incoming and outgoing traffic to prevent unauthorized access and malicious attacks.
        HTTPS (SSL/TLS): Implemented to encrypt communication between clients and servers for data privacy and security.
        Monitoring: Added to monitor the health and performance of the infrastructure, detect issues, and ensure availability.

    Distribution algorithm of the load balancer and how it works:
        The load balancer is configured with a Round Robin distribution algorithm.
        Round Robin distributes incoming requests evenly among available servers in a circular manner.
        This ensures a balanced workload distribution and prevents any single server from being overloaded.

    Active-Active or Active-Passive setup of the load balancer:
        The load balancer is configured in an Active-Active setup.
        Active-Active: All servers actively handle incoming traffic simultaneously.
        Active-Passive: Only one server actively handles traffic while the others remain on standby.
        Active-Active provides better scalability and redundancy compared to Active-Passive.

    How a database Primary-Replica (Master-Slave) cluster works:
        In a Primary-Replica cluster, the Primary Node (Master) accepts write operations and updates the database.
        The Replica Nodes (Slaves) replicate data from the Primary Node and handle read operations.
        This setup ensures data redundancy, high availability, and load balancing.

    Difference between the Primary node and the Replica node in regard to the application:
        The Primary Node handles write operations and updates the database.
        The Replica Nodes handle read operations by serving replicated data from the Primary Node.
        The application interacts with the Primary Node for write operations and with the Replica Nodes for read operations, ensuring efficient load distribution and data consistency.

----
## Problems/Issues
    Where are SPOF (Single Point of Failure):
        The initial infrastructure lacked redundancy, with a single server hosting all components, making it a single point of failure.
        The absence of redundant components such as multiple servers or a load balancer increases the risk of downtime in case of server failure.

    Security issues (no firewall, no HTTPS):
        Lack of firewall exposes the infrastructure to unauthorized access and potential security breaches.
        Absence of HTTPS encryption exposes data transmitted between clients and servers to interception and manipulation by attackers.

    No monitoring:
        Lack of monitoring tools makes it difficult to detect and resolve issues promptly.
        Without monitoring, it's challenging to identify performance bottlenecks, security threats, or infrastructure failures, leading to potential downtime and degraded user experience.