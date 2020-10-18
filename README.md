# Postman collection for customer managed keys and Media Services

This collection is featued as part of the customer managed keys with Media Services tutorial.

## Collection requests and global variables

This collection provides the following REST API requests. They must be run in the sequence provided as some of the requests have test scripts that dynamically create global variables for the next (or subsequent) request in the sequence. In Postman, you will see these variables contained within `{{ }}` brackets.  For example, `{{bearerToken}}`.

1. Get AAD token (sets global variable {{bearerToken}})
2. Get Graph token (sets global variable {{graphToken}})
3. Get Service Principal Details (sets global variable {{servicePrincipalObjectId}})
4. Create a storage account ((sets global variable {{storageAccountId}})
5. Create a Media Services Account with a System Managed Identity (sets global variable {{principalId}})
6. Create a Key Vault, granting access to the service principal (sets global variable {{keyVaultId}})
7. Get a Key Vault token (sets global variable {{keyVaultToken}})
8. Create RSA key in the key vault (sets global variable {{keyId}})
9. Update the Media Services account to use the key with the storage account

Some of the requests have test scripts that dynamically create global variables for the request sequence.

## Getting Started

### Prerequisites

Register an app with Azure Active Directory to establish a service principal with Contributor or higher permissions for use with Postman.

### Installation

1. Run Postman.
2. Select Import.
3. Select Upload files.
4. Navigate to where you have saved this collection.
5. Select this collection.
6. Select Open.  (You will see a warning that it will not be imported as an API, but as a collection, which is fine.  This is what you want.)
7. This collection will now show up in your Collections as BYOK.

Follow the same steps to import the environment file.

### Quickstart
Establish your environment variables in Postman. They will also be used as variables that contained within `{{ }}` brackets.  For example, `{{tenantId}}`.

* *tenantId* = your tenant id
* *servicePrincipalId* = the id of the service principal you establish with your favorite method: portal, CLI, etc.
* *servicePrincipalSecret* = the secret created for the service principal
* *subscription* = your subscription id
* *storageName* = the name you want to give to your storage
* *accountName* = the Media Service account name you want to use
* *keyVaultName* = the Key Vault name you want to use
* *resourceLocation* = centralus (Or where ever you want to put your resources.  This collection has only been tested with centralus.)
* *resourceGroup* = the resource group name

The following variables are standard for working with Azure resources.

* *armResource* = `https://management.core.windows.net`
* *graphResource* = `https://graph.windows.net/`
* *keyVaultResource* = `https://vault.azure.net`
* *armEndpoint* = `management.azure.com`
* *graphEndpoint* = `graph.windows.net`
* *aadEndpoint* = `login.microsoftonline.com`
* *keyVaultDomainSuffix* = `vault.azure.net`

### Send the requests
Once your environment variables have been defined, you can either run the requests one at a time in the above sequence or use Postman's runner to run the collection.
