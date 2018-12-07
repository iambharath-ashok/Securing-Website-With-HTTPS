# Securing-Website-With-HTTPS
A brief instruction about HTTPS, its Role in Securing the Website and how to set up the HTTPS on the Website




## How to setup HTTPS and SSL on the URL


### HTTP - Hyper Text Transfer Protocol

	- 	HTTP is an Internet communication Protocol
	-   Is the method by which data is moved around the Web
		-	  Plus ---> Fast and Reliable 
		- 	Minus ----> Data is not secured and can hack the data in lot of ways that are being transfered from server
		
### HTTPS - Hyper Text Transfer Protocol Secure


	-	Internet Communication Protocol that protects integrity and confidentiality of data b/w user computer and the site

	-	It's a secure protocol on top of HTTP
	-	Provides solution to Data Protection Issues
	-	HTTPS Protects data by encrypting it using SSL Certificate before sending it either way

	
		a). How HTTPS Works?
		
			-	Data sent through HTTPS is secured via TLS - Transport Layer Security Protocol, which provides three key layers of protection
			
				1.	Encryption
				
					-	Encrypting the exchanged data to keep it secure from eavesdroppers
					-	When user is browsing the website nobody can track their activities across multiple pages, listens to their communication
					-	Nobody can steal the information
					
				2.	Data Integrity
					
					-	Data can't be corrupted or modified during transfer - both intentionally or otherwise	
					
				3.	Authentication
				
					-	Proves that users communicate with intended website
					-	It protects against Man-in-Middle attacks
			
	
### SSL Certificate 

	-	A SSL Certificate contains both Private and Public Encryption Key Pairs
	-	These key pairs are like passwords
	-	Keys are long strings of alphanumeric characters used to encrypt the data - so that it's would be very hard to crack
	
	
	Different types of SSL Certificates 
		
		-	Type of SSL Certificate required depends on Business Needs
		-	SSL Certificates are grouped by Validation Level and Level of coverage
	
	
		a).	SSL Certificates by Three Levels of Validation
			
			1.	Domain Validation
			
				- 	Basic Level of validation
				-	SSL Certificates will cause web browser to display a closed lock image next to the website address demonstrating that site is secure
			
			2.	Organization Validation (a.k.a Company Validation)
			
				-  Second Level of validation
				-	The issuer is confirming the fact that the company requesting the certificate does indeed own the rights to the domain for which the certificate is being issued	
			
			3.	Extended Validation

				-	Extended SSL Certificates provides highest level of assurance that a site is legitimate and trustworthy
	
		b).	SSL Certificates by Coverage Level
			
			1.	Single Domain SSL Certificates 
			
				-	One and only domain
				
			2.	Wildcard Domain SSL Certificates
				
				-	Support one domain and all subdomains underneath that domain
				
				
			3.	Mutli Domain SSL Certificates
				
				-	Covers multiple domains

				
### TLS - Transport Layer Security Protocol
	
	- 	Protects data with 3 key layers 
	
		1.	Encryption
		2.	Data Integrity
		3.  Authentication
		
		
### HSTS -	HTTP Strict Transport Security
	
	-	HSTS tells browsers to request HTTPS pages automatically - even when user enters HTTP at the browser bar
	-	Also tells Google Servers to serve secure URLs 
	
		-	HSTS minimizes risk of serving insecure pages 
				
        
1.	Why HTTPS is required?


	-	If we are collecting any sensitive information on our websites like username and password
		-	Then our websites needs to be secured 
	-	Best way to do this by enabling HTTPS, also known as SSL (Secure Socket Layer)
		-	So that any information going from the server is automatically encrypted
	-	This prevents hackers from sniffing out sensitive information as it passes through the internet
	-	HTTPS will be secured by certificates
	
## How to setup HTTPS 

2.	Steps to setting up HTTPS on the websites

	1.	Host Application with a dedicated IP Address
	2.	Buy a Certificate
	3.	Activate the Certificate
	4.	Install the Certificate
	5.	Update your site to use HTTPS
	
	
	1.	Host Application with a dedicated a IP Address
	
		-	SSL Certificates requires dedicated IP Addresses
		-	Smaller Web Hosting plans will put the Application on the shared IP Address
			-	Where multiple websites are using the same location
	
	
	2.	Buy a Certificate
	
		-	Certificate is like ID Card on the site - that tells website is ours
		-	This accomplished by creating a SSL Certificate
		
			a).	What is a Certificate ?
				
				-	A Certificate is simply a paragraph of letters and numbers - thats only our site knows
					-	 It's like a long password
				-	When people visit our site via HTTPS, then that's password will get checked
					-	It automatically verifies that our website is who you say it is
				-	It automatically encrypts all the information that are coming and going from it
		
			b).	How to get a Certificate
			
				-	Technically we can create our own Certificate - called self-signed certificate
				-	Or else we can buy from Certificate Authorities (CA)
					-	Certificate Authorities will also have a copy of Password
					-	Popular Browsers will check with CA to verify the certificate
					-	CA will vouch your site details on the Certificate
					-	In order to recognized from them we need to buy from them
					
	3.	Activate the Certificate
		
		-	Our Web Host can activate the Certificate 
		-	This is a complicated task
		
		a). Activating a Cert by Ourself
		
			-	Generate the CSR - Certificate and Signing Request
			-	We can do this from Web Hosting Control Panel 
			-	Go to Admin Area and choose to Generate Certificate and Signing Request
			-	Fill all the details like EMail, Domain Name
			
		b). Adding CSR to Cert to CA
			
			-	Copy the CSR and give it to the SSL Cert issuer so that they will Establish our Identity
	
	
	4.	Install the Certificate
	
		-	We already have the Certificate in hand and paste that through web host control panel
	
	
	5.	Update the site to use HTTPS
	
		-	Once we access the site via HTTPS then it will start loading 
		-	Enabling HTTPS to few pages like Cart, Checkout will make sense - may result in performance due to encryption processing
		
		
		a).	Updating all links to the target page to HTTPS
		
			-	Selected pages will be given link with HTTPS, so that user while accessing will use HTTPS
		
		
		b).	Do server side redirect to HTTPS irrespective of from user access the pages
		
		
		c).	Mode-rewrite server side approach 
		
		
			-	No need to make any changes in the server side pages 
			-	Change the Apache Configuration
				
				-	This will ensure that any one accessing the page with HTTP will be automatically redirected to HTTPS 
				
	6.	Setup 301 redirects from HTTP to HTTPS or consider HSTS

		-	301 Redirect set up will done at Apache server 
		- 	Automatically redirects the HTTP to HTTPS at server-side
				

Notes :

	1. 	HTTPS doesn't mean that information on the site is secure -	it only means that informations coming and going from server will be secured by encryption
	2.	Ensure high level of security with 2048 bit encryption Certificates
			
			

Search Engine Optimization

	-	Google advices to use HTTPS to whole site 
	-	Doesn't affect the accessibility or performance
	
Changing Your Website Link

	-	Take the advantage of Relative URLs instead of changing all the URLs from HTTP to HTTPS
	
	
Setting up 301 Redirects


	-	301 Redirects both  
		-	Alerts search engines that our site addresses have changed
		-	Redirect any one who has bookmarked a page on our site to HTTPS
		
	-	Configuration	
		
		-	Edit the .htaccess file on the root folder by adding
		
			RewriteEngine On
			RewriteCond %{HTTPS} off
			RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI} [R=301,L]
		
	
	
	
	


			
			
			
			
	
	
