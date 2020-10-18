# Postman collection for customer managed keys and Media Services

These collection and environment files are part of the customer managed keys with Media Services tutorial.

## Collection requests and global variables

This collection provides the following REST API requests. They must be run in the sequence provided as most of the requests have test scripts that dynamically create global variables for the next (or subsequent) request in the sequence. It is not necessary to manually create the global variables.

In Postman, you will see these variables contained within `{{ }}` brackets.  For example, `{{bearerToken}}`.

1. Get AAD token - the test sets the global variable *bearerToken*
2. Get Graph token - the test sets the global variable *graphToken*
3. Get Service Principal Details - the test sets the global variable *servicePrincipalObjectId*
4. Create a storage account - the test sets the global variable *storageAccountId*
5. Create a Media Services Account with a System Managed Identity -  the test sets the global variable *principalId*
6. Create a Key Vault, granting access to the service principal - the test sets the global variable *keyVaultId*
7. Get a Key Vault token - the test sets global variable *keyVaultToken*
8. Create RSA key in the key vault - the test sets global variable *keyId*
9. Update the Media Services account to use the key with the storage account - there is no test script for this request.

## Getting Started

### Prerequisites

Register an app with Azure Active Directory to establish a service principal with Contributor or higher permissions for use with Postman.

### Installation of collection and environment

1. Run Postman.
1. Select **Import**.
1. Select **Upload files**.
1. Navigate to where you have saved the collection and environment files.
1. Select the collection and environment file.
1. Select **Open**.  (You will see a warning that the files will not be imported as an API, but as collections, which is fine.  This is what you want.)
1. This collection will now show up in your Collections as BYOK.
1. The environment variables will now appear in your Environments.

### Quickstart

1. Switch to the environment you just downloaded by selecting the environments dropdown list.
1. Establish your environment variables in Postman. They will also be used as variables that contained within `{{ }}` brackets.  For example, `{{tenantId}}`.

* *tenantId* = your tenant id
* *servicePrincipalId* = the id of the service principal you establish with your favorite method: portal, CLI, etc.
* *servicePrincipalSecret* = the secret created for the service principal
* *subscription* = your subscription id
* *storageName* = the name you want to give to your storage
* *accountName* = the Media Service account name you want to use
* *keyVaultName* = the Key Vault name you want to use
* *resourceLocation* = centralus (Or where ever you want to put your resources.  This collection has only been tested with centralus.)
* *resourceGroup* = the resource group name

The following variables are standard for working with Azure resources so there is no need to change them.

* *armResource* = `https://management.core.windows.net`
* *graphResource* = `https://graph.windows.net/`
* *keyVaultResource* = `https://vault.azure.net`
* *armEndpoint* = `management.azure.com`
* *graphEndpoint* = `graph.windows.net`
* *aadEndpoint* = `login.microsoftonline.com`
* *keyVaultDomainSuffix* = `vault.azure.net`

### Send the requests

Once your environment variables have been defined, you can either run the requests one at a time in the above sequence, or use Postman's runner to run the collection.