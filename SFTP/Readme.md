# Deploy SFTP service in Azure ACI

Deploy [Atmoz Sftp](https://github.com/atmoz/sftp) in ACI, storing files in a storage account located in the same resource group. The files uploaded in the upload folder of the target user, appear in the usernamed Azure File Share of that account.

> WARNING: The password is visible in the ACI properties. You should encrypt it using atmoz/makepasswd as described in https://github.com/atmoz/sftp and then update the template to indicate that the password is encrypted (note the `:e` added there):
> ``` json
> "value": "[concat(parameters('sftpUserName'),':',parameters('sftpPassword'),':e:1001')]"
> ```

## Try on Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Frndazurescript%2FInfrastructureAsCode%2Fmaster%2FSFTP%2Faci-atmoz-sftp.deploy.json)
