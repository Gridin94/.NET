**.NET on windows server:**

In this project we create a ASP.NET Core Web App and run it with
IIS on windows server machine.

*Buid app proccess:*
1. Create new “ASP.NET Core Web App” project in VS.
2. Add “Newtonsoft.Json” from Nuget repository.
3. Restore Nuget Packages.
4. Compile the project.
5. Publish the application.

*Set up the IIS on the windows server:*
1. Add IIS to windows server:
	- Open Server Manager and click Manage > Add Roles and Features. Click Next.
	- Select Role-based or feature-based installation and click Next.
	- Select the appropriate server. The local server is selected by default. Click Next.
	- Enable Web Server (IIS) and click Next.
	- No additional features are necessary to install the Web Adaptor, so click Next.
	- On the Web Server Role (IIS) dialog box, click Next.
	- On the Select role services dialog box, verify that the web server components listed below are enabled:
		**Web Server:**
		1. Common HTTP Features
			- Default Document
			- Static Content
		2. Security
			- Request Filtering
			- Basic Authentication
			- Windows Authentication
		3. Application Development
			- .NET Extensibility 4.5
			- .NET Extensibility
			- ASP.NET 4.5
			- ASP.NET
			- ISAPI Extensions
			- ISAPI Filters
			- WebSocket Protocol
		**Management Tools:**
		1. IIS Management Console
		2. IIS 6 Management Compatibility
			- IIS 6 Metabase Compatibility
		3. IIS Management Scripts and Tools
		4. Management Service
2. Create a new IIS application pool.
3. Create a new website in - "C:\inetpub\wwwroot\", using port 5100 and using our application pool.
4. Copy the published website files from local PC to the windows server - "C:\inetpub\wwwroot\bootcamp".
5. Install .net hosting bundle in the windows server.
6. Browse to “http://localhost:5100/” from the windows server machine.
