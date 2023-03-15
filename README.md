# Azure Policy for CloudShell Tag

Relates to  "Restrict resource creation with an Azure resource policy"
https://learn.microsoft.com/en-us/azure/cloud-shell/persisting-shell-storage#restrict-resource-creation-with-an-azure-resource-policy
tag name:  ms-resource-usage
tag value: azure-cloud-shell




# Azure RBAC on Cloud Shell Storage Accounts
1. Disallow Contributor or Owner permissions at Subscription Scope.
2. Add Contributor Role to user-specific storage account.
3. User creates his/her Azure cloud shell using above existing storage account.

Consider using a cloned Contributor Role at the subscription scope level that denies following:
  Microsoft.Storage/storageAccounts/fileServices/share/read                 NotAction
  Microsoft.Storage/storageAccounts/fileServices/takeOwnership/action       NotDataAction
  Microsoft.Storage/storageAccounts/fileServices/fileshares/files/read      NotDataAction

Ensure no other competing role (such as Owner) is assigned at subscription level without approval



# Unmount or Dismount Cloud Shell Drive
Bash:  clouddrive unmount
PS:   Dismount-CloudDrive




