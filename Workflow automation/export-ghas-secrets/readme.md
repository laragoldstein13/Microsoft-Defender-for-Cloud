# Export GHAS Secrets in Email
**Author: Lara Goldstein**

With this automation playbook, you can notify stakeholders when a new secrets have been discovered through GitHub Advanced Security.

The template in this folder will deploy a LogicApp and a connection to the Office 365.

***

You can deploy the main template by clicking on the buttons below:

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Flaragoldstein13%2FMicrosoft-Defender-for-Cloud%2Fmain%2FWorkflow%2520automation%2Fexport-ghas-secrets%2Fazuredeploy.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>


Once you have deployed all resources, you need to authorize the Office 365 API connection. In addition to that, the Logic App uses a system-assigned Managed Identity to query the APIs used in this playbook. To enable the Logic App for this step, you need to grant the Managed Identity at least Reader rights.

To grant the Managed Identity access rights to the respective scope:
1. Make sure your account has User Access Administrator or Owner permissions for this scope.
2. Go to the subscription/management group page.
3. Press 'Access Control (IAM)' on the navigation bar.
4. Press '+Add' and 'Add role assignment'.
5. Choose Security Reader or Reader role.
6. Assign access to Logic App.
7. Choose the subscription where the logic app was deployed.
8. Choose 'Notify-DevOps-Secrets' Logic App.
9. Press 'save'.

To authorize the API connection:
1. Go to the Resource Group you have used to deploye the template resources.
2. Select the Office365 API connection and press 'Edit API connection'.
3. Press the 'Authorize' button.
4. Make sure to authenticate against Azure AD.
5. Press 'save'.

***
