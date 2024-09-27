# Working with Deliveries in Adobe Campaign Classic Connector

[Overview](#overview) | [Operation Details](#operation-details) 

## Overview

The following operation allows you to work with Deliveries in Adobe Campaign Classic. A Delivery represents a message sent to recipients, such as emails or SMS messages.

| Operation      | Description                              |
|----------------|------------------------------------------|
| createDelivery | Creates a delivery to send Email or SMS messages. |

## Operation Details

This section provides further details on the operation related to Deliveries.

### Creating Deliveries

To create a delivery for sending Email or SMS messages, use `adobeCampaignClassic.createDelivery` and specify the following properties.

#### createDelivery

```xml
<adobeCampaignClassic.createDelivery configKey="MyACCConfig">
    <deliveryType>{$ctx:deliveryType}</deliveryType>
    <subject>{$ctx:subject}</subject>
    <content>{$ctx:content}</content>
    <recipients>{$ctx:recipients}</recipients>
</adobeCampaignClassic.createDelivery>
```

#### Properties

- **deliveryType**: Type of delivery: `Email` or `SMS`. (Required)
- **subject**: Subject of the email or label for the SMS. (Required)
- **content**: Content of the message. (Required)
- **recipients**: Recipients of the message. This should be an XML string defining the recipients. (Required)
- **Additional fields**: Any other delivery fields as needed.

#### Sample Response

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
                  xmlns:xtk="urn:xtk:persist"
                  xmlns:nms="urn:nms:delivery">
   <soapenv:Body>
      <xtk:SaveResponse>
         <pdomOutput>
            <delivery id="54321">
               <messageType>email</messageType>
               <label>Your Email Subject</label>
            </delivery>
         </pdomOutput>
      </xtk:SaveResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

#### Sample Response (SMS Delivery)

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
                  xmlns:xtk="urn:xtk:persist"
                  xmlns:nms="urn:nms:delivery">
   <soapenv:Body>
      <xtk:SaveResponse>
         <pdomOutput>
            <delivery id="54322">
               <messageType>sms</messageType>
               <label>Your SMS Label</label>
            </delivery>
         </pdomOutput>
      </xtk:SaveResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

#### Related Adobe Documentation

[Adobe Campaign Classic - Deliveries](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/deliveries.html)

## Sample Configuration

Below is an example of how to use the `init` operation to establish a connection and then create a delivery.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<proxy xmlns="http://ws.apache.org/ns/synapse"
       name="adobe_create_delivery"
       startOnLoad="true"
       statistics="disable"
       trace="disable"
       transports="http,https">
   <target>
      <inSequence>
         <!-- Initialize Connection -->
         <adobeCampaignClassic.init>
            <username>{$ctx:username}</username>
            <password>{$ctx:password}</password>
            <servername>{$ctx:servername}</servername>
         </adobeCampaignClassic.init>

         <!-- Create Delivery -->
         <adobeCampaignClassic.createDelivery>
            <deliveryType>{$ctx:deliveryType}</deliveryType>
            <subject>{$ctx:subject}</subject>
            <content>{$ctx:content}</content>
            <recipients>{$ctx:recipients}</recipients>
         </adobeCampaignClassic.createDelivery>

         <respond/>
      </inSequence>
      <outSequence>
         <send/>
      </outSequence>
   </target>
   <description/>
</proxy>
```

Replace the placeholders with your actual credentials and delivery data.
