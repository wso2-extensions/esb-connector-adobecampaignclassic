# Configuring Adobe Campaign Classic Operations

[[Prerequisites]](#Prerequisites) [[Adobe Campaign Classic Operations]](#adobe-campaign-classic-operations) [[Logging out of Adobe Campaign Classic]](#logging-out-of-adobe-campaign-classic)

## Prerequisites

### Importing the Adobe Campaign Classic Certificate

To use the Adobe Campaign Classic connector, add the `<adobecampaignclassic.init>` element to your configuration before carrying out any other Adobe Campaign Classic operations.

Before you start configuring the connector, import the Adobe Campaign Classic certificate to your WSO2 Micro Integrator (MI) client keystore.

* Follow the steps below to import the Adobe Campaign Classic certificate into the MI client keystore:

  1. To view the certificate, log in to your Adobe Campaign Classic account in your browser (e.g., https://<adobe-campaign-instance-url>), and click the lock on the address bar.
  2. Export the certificate to the file system.
  3. Import the certificate to the MI client keystore using either the following command or the MI Management Console:
    ```
    keytool -importcert -file <certificate file> -keystore <MI_HOME>/repository/resources/security/client-truststore.jks -alias "AdobeCampaignClassic"
    ```
  4. Restart the server and deploy the following Adobe Campaign Classic configuration:

###### init
```xml
<adobecampaignclassic.init>
    <username>username</username>
    <password>password</password>
    <servername>myserver.adobe-campaign.com</servername>
</adobecampaignclassic.init>
```
###### Properties
* username: The username to access the Adobe Campaign Classic account.
* password: The password for the Adobe Campaign Classic account.
* servername: The server name of the Adobe Campaign Classic account.

```text
*  Users can obtain login credentials by registering in the Adobe Campaign Classic portal or contacting the administrator.
*  The response of this operation is attached to the message body and is used for subsequent Adobe Campaign Classic operations.
*  The session ID is saved in the property adobecampaignclassic.sessionId and the server URL is saved in adobecampaignclassic.serviceUrl. If the login details are invalid, the specified fault sequence is triggered.
```
---
__Note:__

Secure Vault is supported for encrypting passwords. See [Working with Passwords](https://docs.wso2.com/display/ADMIN44x/Encrypting+Passwords+with+Cipher+Tool) for information on integrating and using Secure Vault.

---
**Re-using Adobe Campaign Classic configurations**

You can save the Adobe Campaign Classic connection configuration as a [local entry](https://docs.wso2.com/display/EI620/Working+with+Local+Registry+Entries) and then easily reference it with the `configKey` attribute in your operations. For example, if you saved the above `<adobecampaignclassic.init>` entry as a local entry named `MyACCConfig`, you could reference it from an operation like `getUserInfo` as follows:

```xml
<adobecampaignclassic.getUserInformation configKey="MyACCConfig"/>
```
The Adobe Campaign Classic connector operation examples use this convention to show how to specify the connection configuration for that operation. In all cases, the `configKey` attribute is optional if the connection to Adobe Campaign Classic has already been established and is required only if you need to specify a different connection from the current connection.

## Adobe Campaign Classic Operations

Now that you have connected to Adobe Campaign Classic, use the information in the following topics to perform various operations with the connector.

[Working with Profiles](profiles.md)

[Working with Deliveries](deliveries.md)

[Working with Workflows](workflows.md)
