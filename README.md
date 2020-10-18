# Postman collection for customer managed keys and Media Services

This collection is featued as part of the customer managed keys with Media Services tutorial.

## Features

This collection provides the following REST API requests:

* Get AAD token
* Get Graph token
* Get Service Principal Details
* Create a storage account
* Create a Media Services Account with a System Managed Identity
* Create a Key Vault, granting access to the service principal
* Get a Key Vault token
* Create RSA key in the key vault
* Update the Media Services account to use the key with the storage account

## Getting Started

### Prerequisites

Register an app with Azure Active Directory to establish a service principal with Contributor or higher permissions for use with Postman.

### Installation

1. Run Postman.
2. Select Import.
3. Select Upload files.
4. Navigate to where you have saved this collection.
5. Select this collection.
6. Select Open.  (You will see a warning that it will not be imported as an API, but as a collection, which is fine.  That is what you want.)
7. This collection will now show up in your Collections as BYOK.

### Quickstart
Establish your environment variables in Postman. The will be used as the variables that are contained within {{ }} brackets.  For example {{tenantId}}.

tenantId = your tenant id
servicePrincipalId = the id of the service principal you establish with your favorite method: portal, CLI, etc.
servicePrincipalSecret = the secret created for the service principal
subscription = your subscription id
armResource = `https://management.core.windows.net`
graphResource = `https://graph.windows.net/`
keyVaultResource = `https://vault.azure.net`
armEndpoint = `management.azure.com`
graphEndpoint = `graph.windows.net`
aadEndpoint = `login.microsoftonline.com`
keyVaultDomainSuffix = `vault.azure.net`
storageName = the name you want to give to your storage
accountName = the Media Service account name you want to use
keyVaultName = the Key Vault name you want to use
resourceLocation = centralus (Or where ever you want to put your resources.  This collection has only been tested with centralus.)
resourceGroup = the resource group name
