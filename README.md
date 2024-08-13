# Configuring Application Proxy Configuration
if all the devices will be locally you can skip this step, otherwise to connect as of now you would need to punch a whole in the firewall,
to get your scep url out of to the internet, which is not recommended for security reasons. therefore you can add proxy.
Go to this Azure Active Directory, > Application Proxy > Download Connector Service > Accept terms & Download the app
![image](https://github.com/user-attachments/assets/d126a4a0-cdce-44b1-a843-b47097daa14e) <br/>

Install the app in the NDES Server:  <br/>
![image](https://github.com/user-attachments/assets/341c8725-67b4-40e4-9467-0d985b4c0b04) <br/>
Sign-In with a Global Admin Account  <br/>
![image](https://github.com/user-attachments/assets/5e381f9e-c4fc-4f3b-a1af-f77768d6b699) <br/>
![image](https://github.com/user-attachments/assets/a06b37a9-12ba-4f7f-81ee-7c9f2f351293) <br/>
this will install 2 apps in the control panel. <br/>
![image](https://github.com/user-attachments/assets/ea1cab63-2235-44c1-91f7-32214e010c4e) <br/>
Wait for about 5 minutes this will replicate back in Azure <br/>
then you will see the endpoint being active, now `Configure the app` <br/>
![image](https://github.com/user-attachments/assets/c8afa305-bc09-47d1-9728-0103864e0246) <br/>
Add the below settings: <br/>
![image](https://github.com/user-attachments/assets/65ec76f6-9b29-45ff-8ca7-3457678e860d) <br/>
![image](https://github.com/user-attachments/assets/c10205b8-7ea1-4f77-b454-0213fc023279) <br/>
then click create.
if you go to the External URL, you should be able to hit the IIS Default site, 
while having a certificate from Entra Proxy ie. https://ndesproxy1-mngenvmcap153138.msappproxy.net/<br/>
![image](https://github.com/user-attachments/assets/8d6daf4c-eb44-4b70-af34-41471d1c7f5c) <br/>

The URL that you will use towards the scep would be `External URL + /certsrv/mscep/mscep.dll`
[https://ndesproxy1-mngenvmcap153138.msappproxy.net//certsrv/mscep/mscep.dll](https://ndesproxy1-mngenvmcap153138.msappproxy.net/certsrv/mscep/mscep.dll)

If this is done correctly then you should be able to see the below:  <br/>
![image](https://github.com/user-attachments/assets/236e8895-1653-4ee7-9f7e-3e1a4e4a171a) <br/>

it is expected by design to get the error from the Ndes server this time, as opposed getting the 403 error from the browser itself.

👉Tip: re-configing the app.
Uninstall the app from the server then you will see the URL will become inactive after few minutes, 
then re-install the app then you will see the app being able to edit.
