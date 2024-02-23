# Task 0

-----
## 0. Simple web stack
A lot of websites are powered by simple web infrastructure, a lot of time it is composed of a single server with a [LAMP stack](https://intranet.alxswe.com/rltoken/YVDX0XsC6XHp0nmezvT9vQ).

On a whiteboard, design a one server web infrastructure that hosts the website that is reachable via `www.foobar.com`. Start your explanation by having a user wanting to access your website.

Requirements:

	* You must use:
		* 1 server
		* 1 web server (Nginx)
		* 1 application server
		* 1 application files (your code base)
		* 1 database (MySQL)
		* 1 domain name `foobar.com` configured with a `www` record that points to your server IP `8.8.8.8`
	* You must be able to explain some specifics about this infrastructure:
		* What is a server
		* What is the role of the domain name
		* What type of DNS record `www is in `www.foobar.com`
		* What is the role of the web server
		* What is the role of the application server
		* What is the role of the database
		* What is the server using to communicate with the computer of the user requesting the website
	* You must be able to explain what the issues are with this infrastructure:
		* SPOF
		* Downtime when maintenance needed (like deploying new code web server needs to be restarted)
		* Cannot scale if too much incoming traffic

Please, remember that everything must be written in English to further your technical ability in a variety of settings.

------
## Explanation
1. **What is a server:** A server is a computer program or device that provides functionality for other programs or devices, known as clients. In the context of this infrastructure, the server refers to the physical or virtual machine that hosts the website and its components, such as the web server, application server, and database server.
2. **What is the role of the domain name:** The domain name serves as a human-readable address that maps to the IP address of the server hosting the website. It helps users locate and access the website easily. In this case, the domain name "www.foobar.com" points to the server's IP address (e.g., 8.8.8.8).
3. **What type of DNS record `www` is in `www.foobar.com`:** The "www" in "www.foobar.com" is typically configured as a subdomain, and it is commonly associated with the web server hosting the website. The DNS record for "www" can be either a CNAME (Canonical Name) record, which points to the main domain name ("foobar.com"), or an A record (IPv4 address) that specifies the IP address of the server.
4. **What is the role of the web server:** The web server's role is to handle incoming HTTP requests from clients (e.g., web browsers) and serve web pages and other static content in response to those requests. It manages connections, processes requests, and sends back appropriate responses to clients.
5. **What is the role of the application server:** The application server's role is to execute server-side code, handle business logic, and generate dynamic content in response to client requests. It hosts the web application and interacts with databases or other external services to process and fulfill user requests.
6. **What is the role of the database:** The database's role is to store and manage the structured data used by the web application. It provides a persistent storage solution for user information, content, configurations, and other relevant data. The database allows the application server to retrieve and manipulate data dynamically.
7. **What is the server using to communicate with the computer of the user requesting the website:** The server communicates with the user's computer over the internet using the HTTP (Hypertext Transfer Protocol) protocol. When a user requests a website, their web browser sends an HTTP request to the server, specifying the URL of the requested resource. The server processes the request, generates the appropriate response (typically an HTML page), and sends it back to the user's browser over HTTP.

-------
## Problems/Issues
1. **SPOF:** The infrastructure has a single server hosting all components, which becomes a single point of failure. If the server fails or experiences issues, the entire website becomes inaccessible, leading to downtime and potential loss of business.
2. **Downtime when maintenance needed (like deploying new code web server needs to be restarted):** Performing maintenance tasks, such as deploying new code or restarting the web server, may result in downtime. During maintenance, the website may be unavailable to users, impacting user experience and potentially causing frustration.
3. **Cannot scale if too much incoming traffic:** The infrastructure may struggle to handle large spikes in incoming traffic, leading to performance issues or website downtime. Without scalable infrastructure and proper load balancing, the server may become overwhelmed during peak traffic periods, resulting in degraded performance or complete unavailability for users.