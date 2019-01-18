# Firebase Hosting Custom Domain with GoDaddy

Documentation on how to config an environtment for this deploy type. Recenly we had to config it, and this implementation depends of Domain provider. 
My domain (example) www.foo.com.co intially point to a on premise Web Portal, and with a new deploy on firebase we needed to redirect a new subdomain (subdomain.foo.com.co) to a Firebase hosting.

## Getting Started

* Inside Godaddy, login with your account
* In "Domains" section, select "DNS" on the domain that you need config
![alt text](https://github.com/mayusGomez/FirebaseCustomDomainGodaddy/raw/master/01-DNSmanage.png)
* The initial GoDaddy's configuration was: 
![alt text](https://github.com/mayusGomez/FirebaseCustomDomainGodaddy/raw/master/02-InitialConfig.png)
* Then we need to login into Firebase console, select the project and the "Hosting Option"
* Into hosting option, we need to select the option "Connect domain":
![alt text](https://github.com/mayusGomez/FirebaseCustomDomainGodaddy/raw/master/03-FirebaseConnetDomain.png)
* In the modal, we need to insert the domain that we need to config:
![alt text](https://github.com/mayusGomez/FirebaseCustomDomainGodaddy/raw/master/04-FirebaseInsertDom.png)
* Firebase give you a TXT string to insert into GoDaddy, we need to go to GoDaddy and select the option "ADD", then select the option "type"="TXT", "host"="@" and "TXT Value"="Firebase string":
![alt text](https://github.com/mayusGomez/FirebaseCustomDomainGodaddy/raw/master/05-FirebaseTXTConfig.PNG)
* Then, we need to indicate to Firebase that TXT configuration is done, and continue with validation. It could take a few minutes, but have patience. Then Firebase confirm your domain ownership and let you continue with the configuration:
![alt text](https://github.com/mayusGomez/FirebaseCustomDomainGodaddy/raw/master/06-FirebaseConfigToGodaddy.PNG)
* Then in Godaddy, we need to select the option "ADD", with the options: "Type"="A", "Host"="only subdamin's name", "Points to"="IP's provided by firebase", this operation by each IP that firebase give to us:
![alt text](https://github.com/mayusGomez/FirebaseCustomDomainGodaddy/raw/master/07-GoDaddyConfig.PNG)
* After that only have to wait for enter to our subdomain deploy on firebase, initially we going to view without SSL, but after a time firebase will assign a certificate (Let's Encrypt) to us.
