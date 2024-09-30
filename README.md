# Adobe Campaign Classic MI Connector

The Adobe Campaign Classic [Connector](https://docs.wso2.com/display/EI650/Working+with+Connectors) allows you to integrate WSO2 Micro Integrator (WSO2 MI) with the [Adobe Campaign Classic SOAP API](https://experienceleague.adobe.com/en/docs/campaign-classic/using/campaign-classic-home), enabling interaction with the marketing campaign automation platform. Adobe Campaign Classic helps businesses manage marketing campaigns, including customer data management, campaign orchestration, and real-time interaction. Using this connector, you can create, update, retrieve, and manage marketing data and campaigns within Adobe Campaign Classic via WSO2 MI.

## Compatibility

| Connector Version | Supported Adobe Campaign SOAP API Version | Supported WSO2 MI Version                |
|-------------------| ------------------------------------------ | ---------------------------------------- |
| 0.1.0             | 6.1.1                                      | WSO2 Micro Integrator for VS Code V1     |

## Getting Started

### Download and Install the Connector

1. Download the Adobe Campaign Classic connector from the [WSO2 Store](https://store.wso2.com/store/assets/esbconnector) by clicking the "Download Connector" button.
2. Follow the [Working with Connectors via the Management Console](https://docs.wso2.com/display/EI650/Working+with+Connectors+via+the+Management+Console) guide to add and enable the connector in your WSO2 MI instance.
3. For more information on configuring connectors and their operations in your configurations, refer to [Using a Connector](https://docs.wso2.com/display/EI650/Using+a+Connector).
4. WSO2 MI for VS Code, refer to the documentation on [MI for VS Code](https://mi.docs.wso2.com/en/latest/develop/mi-for-vscode/mi-for-vscode-overview/).

### Configuring the Connector Operations

To get started with the Adobe Campaign Classic connector and its operations, see the [Configuring Adobe Campaign Classic Operations](connector/docs/config.md).

## Building From the Source

If you prefer building the Adobe Campaign Classic connector from the source code:

1. Clone or download the source code from [GitHub](https://github.com/wso2-extensions/esb-connector-adobecampaignclassic).
2. Navigate to the `esb-connector-adobecampaignclassic/connector` directory.
3. Run the following Maven command: `mvn clean install`.
4. The Adobe Campaign Classic connector zip file will be created under the `esb-connector-adobecampaignclassic/connector/target` directory.

## How You Can Contribute

WSO2 welcomes community contributions. Check the [issue tracker](https://github.com/wso2-extensions/esb-connector-adobe-campaign/issues) for open issues and submit your contributions to help improve the connector. We look forward to your participation!
