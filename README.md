# Deploy a logic app that can be used in Azure Active Directory Identity Governance Entitlement Management custom action (preview)

![Azure Public Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/demos/identitygovernance-entitlementmanagement-extensibility-sample-logicapp/PublicLastTestDate.svg)
![Azure Public Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/demos/identitygovernance-entitlementmanagement-extensibility-sample-logicapp/PublicDeployment.svg)

![Azure US Gov Last Test Date](https://azurequickstartsservice.blob.core.windows.net/badges/demos/identitygovernance-entitlementmanagement-extensibility-sample-logicapp/FairfaxLastTestDate.svg)
![Azure US Gov Last Test Result](https://azurequickstartsservice.blob.core.windows.net/badges/demos/identitygovernance-entitlementmanagement-extensibility-sample-logicapp/FairfaxDeployment.svg)

![Best Practice Check](https://azurequickstartsservice.blob.core.windows.net/badges/demos/identitygovernance-entitlementmanagement-extensibility-sample-logicapp/BestPracticeResult.svg)
![Cred Scan Check](https://azurequickstartsservice.blob.core.windows.net/badges/demos/identitygovernance-entitlementmanagement-extensibility-sample-logicapp/CredScanResult.svg)

 [![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fvikama-microsoft%2Felmcustomextensions%2Fmain%2Fazuredeploy-withOutOms.json)
[![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fvikama-microsoft%2Felmcustomextensions%2Fmain%2Fazuredeploy.json)

 [![Logic with MSI and Resume](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fvikama-microsoft%2Felmcustomextensions%2Fmain%2FazureDeploy-request-sysmsi-resume-withoutoms.json)

  [![Logic with MSI and Resume](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Figaelmprodportalhosting.blob.core.windows.net%2Farm-deployment-template%2Flogicapp-pop-assignmentRequest-azureDeploy-sysmsi-resume-withoutoms.json)


This template creates a simple logic app with all the authorization policy settings and schema to http trigger that is needed by Azure AD entitlement management custom action API.

Below are the parameters that the template expects.

| Name   | Description    |
|:--- |:---|
| name  | Name for the logic app. |
| catalogId  | CatalogId of the Azure AD entitlement management catalog, where you are going to use this logic app.  |

Then, the arm template will achieve the following:
 * Create a logic app
 * Add authorization policy settings to verify Entitlement Management call  
 * Policy setting has the Entitlement Management first party appid (810dcf14-1858-4bf2-8134-4c369fa3235b), to verify that it is Entitlement Management which is calling this logic app.
 * And finally, adds schema to http trigger to match the message schema that is used by Entitlement Management
