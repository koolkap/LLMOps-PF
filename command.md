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