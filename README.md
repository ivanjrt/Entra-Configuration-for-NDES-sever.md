# Configuring Application Proxy Configuration
if all the devices will be locally you can skip this step, otherwise to connect as of now you would need to punch a whole in the firewall,
to get your scep url out of to the internet, which is not recommended for security reasons. therefore you can add proxy.
Go to this Azure Active Directory, > Application Proxy > Download Connector Service > Accept terms & Download the app
![image](https://github.com/user-attachments/assets/2ecc3316-8c7f-4657-b156-e7cc7c6205f9)  <br/>

Install the app in the NDES Server: `MicrosoftEntraPrivateNetworkConnectorInstaller.msi`  <br/>
![image](https://github.com/user-attachments/assets/91a27b81-dd95-48a7-891c-7bf546d79082)  <br/>
Sign-In with a Global Admin Account  <br/>
![image](https://github.com/user-attachments/assets/6e46704f-8ae1-4242-917a-389a93244f0c) <br/>
![image](https://github.com/user-attachments/assets/8eef11e5-4575-4897-bee5-a9b56b4f6fbf) <br/>
this will install 2 apps in the control panel. <br/>
![image](https://github.com/user-attachments/assets/56ead2f5-2d74-434b-90ca-5ccdc92af1c1) <br/>
Wait for about 5 minutes this will replicate back in Azure <br/>
then you will see the endpoint being active, now `Configure the app` <br/>
![image](https://github.com/user-attachments/assets/1bd17a14-8e67-4bae-9998-5a02c17e031e) <br/>
Add the below settings: <br/>
![image](https://github.com/user-attachments/assets/d4dba27d-e574-43b9-bf0c-76bcfc1a3d9e) <br/>
![image](https://github.com/user-attachments/assets/ad5dec02-a5e7-470a-bf0e-971e7a3ac874) <br/>
then click create.
if you go to the External URL, you should be able to hit the IIS Default site, 
while having a certificate from Entra Proxy ie. https://ndesproxy1-mngenvmcap153138.msappproxy.net/<br/>
![image](https://github.com/user-attachments/assets/32e28540-3441-423b-b782-12fd06f5e69a) <br/>

The URL that you will use towards the scep would be `External URL + /certsrv/mscep/mscep.dll` <br/>
ie: [https://ndesproxy1-mngenvmcap153138.msappproxy.net//certsrv/mscep/mscep.dll]

If this is done correctly then you should be able to see the below:  <br/>
![image](https://github.com/user-attachments/assets/37159be9-7e20-4d78-953c-1999b75b11f2) <br/>

it is expected by design to get the error from the Ndes server this time, as opposed getting the 403 error from the browser itself.

👉Tip: re-configing the app.
Uninstall the app from the server then you will see the URL will become inactive after few minutes, 
then re-install the app then you will see the app being able to edit.
