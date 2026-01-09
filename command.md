projectName="my-prompt-flow"
roleName="Contributor"
subscriptionId="49251aaf-72f7-4fc7-a8de-bad3e34289b5"
environment="<Prod>" #First letter should be capitalized
servicePrincipalName="Azure-ARM-${environment}-${projectName}"
# Verify the ID of the active subscription
echo "Using subscription ID $subscriptionID"
echo "Creating SP for RBAC with name $servicePrincipalName, with role $roleName and in scopes /subscriptions/$subscriptionID"
az ad sp create-for-rbac --name $servicePrincipalName --role $roleName --scopes /subscriptions/$subscriptionID
echo "Please ensure that the information created here is properly save for future use."


az ad sp create-for-rbac  --name "MyPromptFlowSP"  --role Contributor  --scopes /subscriptions/49251aaf-72f7-4fc7-a8de-bad3e34289b5

az ad sp create-for-rbac --name "gh-actions-pf" --role contributor --scopes /subscriptions/49251aaf-72f7-4fc7-a8de-bad3e34289b5 --sdk-auth



List of the machine 

az ml workspace list -o table use this command

{
  "clientId": "603c21b1-0114-430c-b873-74c7e1d4258f",
  "clientSecret": "vzg8Q~5ovWC8epFOChYo3~1wOpNCeKgxfx3Wzddu",
  "subscriptionId": "49251aaf-72f7-4fc7-a8de-bad3e34289b5",
  "tenantId": "3eeb1469-c780-45e3-81f6-92f875051561",
  "activeDirectoryEndpointUrl": "https://login.microsoftonline.com",
  "resourceManagerEndpointUrl": "https://management.azure.com/",
  "activeDirectoryGraphResourceId": "https://graph.windows.net/",
  "sqlManagementEndpointUrl": "https://management.core.windows.net:8443/",
  "galleryEndpointUrl": "https://gallery.azure.com/",
  "managementEndpointUrl": "https://management.core.windows.net/"
}

az login --service-principal --username 603c21b1-0114-430c-b873-74c7e1d4258f --password vzg8Q~5ovWC8epFOChYo3~1wOpNCeKgxfx3Wzddu --tenant 3eeb1469-c780-45e3-81f6-92f875051561


pf  runtime list --subscription "49251aaf-72f7-4fc7-a8de-bad3e34289b5" -g "app-insight-rg" -w "prompt-flow-app"
