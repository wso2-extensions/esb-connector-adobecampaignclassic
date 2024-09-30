
# Workflows.md

# Working with Workflows in Adobe Campaign Classic Connector

[Overview](#overview) | [Operation Details](#operation-details) | [Sample Configuration](#sample-configuration)

## Overview

The following operations allow you to control Workflows in Adobe Campaign Classic. Workflows automate tasks such as data management and campaign execution.

| Operation       | Description                          |
|-----------------|--------------------------------------|
| [startWorkflow](#starting-workflows) | Starts a specified workflow. |
| [stopWorkflow](#stopping-workflows)  | Stops a specified workflow.  |

---

## Operation Details

This section provides further details on the operations related to Workflows.

### Starting Workflows

To start a workflow, use `adobeCampaignClassic.startWorkflow` and specify the following properties.

#### startWorkflow

```xml
<adobeCampaignClassic.startWorkflow configKey="MyACCConfig">
    <workflowId>{$ctx:workflowId}</workflowId>
</adobeCampaignClassic.startWorkflow>
```

#### Properties

- **workflowId**: ID of the workflow to start. (Required)

#### Sample Response

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
                  xmlns:xtk="urn:xtk:workflow">
   <soapenv:Body>
      <xtk:StartResponse>
         <workflow id="1001" state="started"/>
      </xtk:StartResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

### Stopping Workflows

To stop a workflow, use `adobeCampaignClassic.stopWorkflow` and specify the following properties.

#### stopWorkflow

```xml
<adobeCampaignClassic.stopWorkflow configKey="MyACCConfig">
    <workflowId>{$ctx:workflowId}</workflowId>
</adobeCampaignClassic.stopWorkflow>
```

#### Properties

- **workflowId**: ID of the workflow to stop. (Required)

#### Sample Response

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
                  xmlns:xtk="urn:xtk:workflow">
   <soapenv:Body>
      <xtk:StopResponse>
         <workflow id="1001" state="stopped"/>
      </xtk:StopResponse>
   </soapenv:Body>
</soapenv:Envelope>
```
