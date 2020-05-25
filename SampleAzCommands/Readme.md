# Deploy ARM templates via powershell

```
# The AAD Tenant ID found at https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview
$tenantId = 'ab07ab07-ab07-ab07-ab07-ab07ab07ab07'
# The subscription ID where the resource groups exists
$subscriptionId = 'ab07ab07-ab07-ab07-ab07-ab07ab07ab07'
#Login to specific subscription in the specific tenant
Connect-AzAccount -Subscription $subscriptionId  -Tenant $tenantId

# Deploy ARM template with parameter file
New-AzResourceGroupDeployment -TemplateFile ./template.json -TemplateParameterFile ./dev-env.params.json -ResourceGroupName "sample-arm-template-rg"

# Another example where I pass the variables through arguments
# Also note the incremental deployment mode
New-AzResourceGroupDeployment -Mode Incremental `
          -TemplateFile "pipeline_010_Storage.deploy.json" `
          -ResourceGroupName $ResourceGroupName `
          -resourceName $StorageName
```
