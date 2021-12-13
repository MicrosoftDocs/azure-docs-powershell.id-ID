---
title: Panduan migrasi untuk Az 7.0.0
description: Panduan migrasi ini berisi daftar perubahan terbaru yang dibuat Azure PowerShell rilis Az versi 7.0.0.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 12/07/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 777791c6854e9320ef4b748a5ae187bab7d5ff77
ms.sourcegitcommit: 167a959fbb45f819467b7d71a62b20ccb10f39c0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/13/2021
ms.locfileid: "134683757"
---
# <a name="migration-guide-for-az-700"></a>Panduan Migrasi untuk Az 7.0.0

## <a name="azaccounts"></a>Az.Accounts

### <a name="context-and-account-cmdlets"></a>Konteks dan cmdlet akun

Output cmdlet berikut telah diubah:
- Get-AzContext
- Remove-AzContext
- Rename-AzContext
- Select-AzContext
- Connect-AzAccount
- Disconnect-AzAccount
- Import-AzContext
- Save-AzContext

Dihapus `ServicePrincipalSecret` dan `CertificatePassword` di `PSAzureRmAccount`

#### <a name="before"></a>Sebelum
```powershell
PS C:\> $cred = Get-Credential
PS C:\> Connect-AzAccount -ServicePrincipal -Tenant 54826b22-xxxx-xxxx-xxxx-xxxxxxxxxxxxx -Credential $cred
PS C:\> (Get-AzContext).Account.ExtendedProperties

Key                    Value
---                    -----
CertificatePath        C:\certificate.pfx
CertificatePassword    password****
Tenants                54826b22-xxxx-xxxx-xxxx-xxxxxxxxxxxxx
ServicePrincipalSecret 7QK7Q********************************
Subscriptions          0b1f6471-xxxx-xxxx-xxxx-xxxxxxxxxxxxx
```
#### <a name="after"></a>Setelah
```powershell
PS C:\> $cred = Get-Credential
PS C:\> Connect-AzAccount -ServicePrincipal -Tenant 54826b22-xxxx-xxxx-xxxx-xxxxxxxxxxxxx -Credential $cred
PS C:\> (Get-AzContext).Account.ExtendedProperties

Key             Value
---             -----
CertificatePath C:\certificate.pfx
Tenants         54826b22-xxxx-xxxx-xxxx-xxxxxxxxxxxxx
Subscriptions   0b1f6471-xxxx-xxxx-xxxx-xxxxxxxxxxxxx
```


## <a name="azaks"></a>Az.Aks

### `Get-AzAksVersion`
Properti `Upgrades` dalam output diubah menjadi `Upgrade` .

#### <a name="before"></a>Sebelum
```powershell
PS C:\> (Get-AzAksVersion -location eastus).Upgrades

OrchestratorType OrchestratorVersion IsPreview
---------------- ------------------- ---------
Kubernetes       1.19.13
Kubernetes       1.20.7
Kubernetes       1.20.9
Kubernetes       1.20.7
Kubernetes       1.20.9
Kubernetes       1.20.9
Kubernetes       1.21.1
Kubernetes       1.21.2
Kubernetes       1.21.1
Kubernetes       1.21.2
Kubernetes       1.21.2
Kubernetes       1.22.1              True
Kubernetes       1.22.2              True
Kubernetes       1.22.1              True
Kubernetes       1.22.2              True
Kubernetes       1.22.2              True
```
#### <a name="after"></a>Setelah
```powershell
PS C:\> (Get-AzAksVersion -location eastus).Upgrade

OrchestratorType OrchestratorVersion IsPreview
---------------- ------------------- ---------
Kubernetes       1.19.13
Kubernetes       1.20.7
Kubernetes       1.20.9
Kubernetes       1.20.7
Kubernetes       1.20.9
Kubernetes       1.20.9
Kubernetes       1.21.1
Kubernetes       1.21.2
Kubernetes       1.21.1
Kubernetes       1.21.2
Kubernetes       1.21.2
Kubernetes       1.22.1              True
Kubernetes       1.22.2              True
Kubernetes       1.22.1              True
Kubernetes       1.22.2              True
Kubernetes       1.22.2              True
```


## <a name="azcontainerinstance"></a>Az.ContainerInstance

### `New-AzContainerGroup`
Parameter networkProfileId yang dihapus, ditambahkan SubnetId sebagai alternatifnya

#### <a name="before"></a>Sebelum
```powershell
PS C:\>  $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -OsType Linux -NetworkProfileId "/subscriptions/{subId}/resourceGroups/{rg}/providers/Microsoft.Network/virtualNetworks/{vnetName}/subnets/{subnetName}"
PS C:\> $containerGroup.NetworkProfileId

/subscriptions/{subId}/resourceGroups/{rg}/providers/Microsoft.Network/virtualNetworks/{vnetName}/subnets/{subnetName}
```
#### <a name="after"></a>Setelah
```powershell
PS C:\> $container = New-AzContainerInstanceObject -Name test-container -Image nginx
PS C:\> $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -OsType Linux -RestartPolicy "Never" -IpAddressType 'Private' -SubnetId @{"Id"="/subscriptions/{subId}/resourceGroups/{rg}/providers/Microsoft.Network/virtualNetworks/{vnetName}/subnets/{subnetName}"; "Name"="subnet"}
PS C:\> $containerGroup.SubnetId | fl

Id :  /subscriptions/{subId}/resourceGroups/{rg}/providers/Microsoft.Network/virtualNetworks/{vnetName}/subnets/{subnetName}
Name : subnet
```


### `Invoke-AzContainerInstanceCommand`
Hasil eksekusi perintah yang ditampilkan sebagai output cmdlet dengan menyambungkan websocket dalam backend

#### <a name="before"></a>Sebelum
```powershell
PS C:\> $websocket = Invoke-AzContainerInstanceCommand -ContainerGroupName test-cg -ContainerName test-container -ResourceGroupName　test-rg -Command "echo hello" -TerminalSizeCol 12 -TerminalSizeRow 12
PS C:\> $websocket

Password                                           WebSocketUri
--------                                           ------------
****************** wss://bridge-linux-xx.eastus.management.azurecontainer.io/exec/caas-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx/bridge-xxxxxxxxxxxxxxx?rows=12&cols=12api-version=2018-02-01-preview

User needs connect websocket using password to fetch command execution result
```
#### <a name="after"></a>Setelah
```powershell
PS C:\> Invoke-AzContainerInstanceCommand -ContainerGroupName test-cg -ContainerName test-container -ResourceGroupName　test-rg -Command "echo hello"

hello
```


## <a name="azfunctions"></a>Az.Functions

### `Update-AzFunctionApp, Update-AzFunctionAppPlan`
`Update-AzFunctionApp` akan meminta konfirmasi. Perilaku ini bisa dilewati dengan menentukan `-Force` .

#### <a name="before"></a>Sebelum
```powershell
Update-AzFunctionApp -Name MyUniqueFunctionAppName -ResourceGroupName MyResourceGroupName -PlanName NewPlanName
```
#### <a name="after"></a>Setelah
```powershell
Update-AzFunctionApp -Name MyUniqueFunctionAppName -ResourceGroupName MyResourceGroupName -PlanName NewPlanName -Force
```


### `New-AzFunctionApp`
Jika `FunctionsVersion` parameter tidak ditentukan saat menjalankan `New-AzFunctionApp` cmdlet, versi Fungsi default akan diatur ke `4` .

```
There is no change to the usage.
```

### `Remove-AzFunctionApp`
Jika ini adalah aplikasi terakhir di paket layanan aplikasi, paket tersebut tidak akan dihapus. Sebelum rilis ini, paket aplikasi juga akan dihapus.

```
There is no change to the usage.
```

## <a name="azhdinsight"></a>Az.HDInsight

### `New-AzHDInsightCluster`
Mengubah tipe parameter "OSType" `Microsoft.Azure.Management.HDInsight.Models.OSType` dari menjadi `System.string`

```
There is no change to the usage.
```


### `New-AzHDInsightCluster, New-AzHDInsightClusterConfig`
Mengubah tipe parameter "ClusterTier" `Microsoft.Azure.Management.HDInsight.Models.ClusterTier` dari menjadi `System.string`

```
There is no change to the usage.
```


### `Set-AzHDInsightClusterDiskEncryptionKey, Set- AzHDInsightClusterSize`
Tipe output telah berubah dari 'Microsoft.Azure.Management.HDInsight.Models.Cluster' menjadi 'Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightCluster'.

```
All properties remain the same, so there is no change to the usage.
```



### `Cluster cmdlets`
Tipe properti 'AssignedIdentity' telah berubah dari 'Microsoft.Azure.Management.HDInsight.Models.ClusterIdentity' menjadi 'Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightClusterIdentity'.


```
All properties remain the same, so there is no change to the usage.
```


### `Get-AzHDInsightProperties`
Tipe generik untuk output 'properti VmSizes' telah diubah `System.Collections.Generic.IDictionary2[System.String,Microsoft.Azure.Commands.HDInsight.Models.Management.AzureHDInsightVmSizesCapability]` dari ke `System.Collections.Generic.IList1[System.String]` .

#### <a name="before"></a>Sebelum
```powershell
PS C:\> $result = Get-AzHDInsightProperty -Location "South Central us"
PS C:\> $availableVmSizes = $result.VmSizes['iaas'].AvailableVmSizes
```
#### <a name="after"></a>Setelah
```powershell
PS C:\> $result = Get-AzHDInsightProperty -Location "South Central us"
PS C:\> $availableVmSizes = $result.VmSizes
```


## <a name="azkeyvault"></a>Az.KeyVault

### `New-AzKeyVaultRoleDefinition, Get-AzKeyVaultRoleDefinition`
Properti berikut dalam `PSKeyVaultPermission` model diubah namanya:
- `AllowedActions` -> `Actions`
- `DeniedActions` -> `NotActions`
- `AllowedDataActions` -> `DataActions`
- `DeniedDataActions` -> `NotDataActions`

#### <a name="before"></a>Sebelum
```powershell
PS C:\> $backupRole = Get-AzKeyVaultRoleDefinition -HsmName myHsm -RoleDefinitionName "Managed HSM Backup User"

PS C:\> $backupRole.Permissions

AllowedActions DeniedActions AllowedDataActions DeniedDataActions
-------------- ------------- ------------------ -----------------
0 action(s)    0 action(s)   3 action(s)        0 action(s)

PS C:\> $backupRole.Permissions.AllowedDataActions

Microsoft.KeyVault/managedHsm/backup/start/action
Microsoft.KeyVault/managedHsm/backup/status/action
Microsoft.KeyVault/managedHsm/keys/backup/action
```
#### <a name="after"></a>Setelah
```powershell
PS C:\> $backupRole = Get-AzKeyVaultRoleDefinition -HsmName myHsm -RoleDefinitionName "Managed HSM Backup User"

PS C:\> $backupRole.Permissions

Actions     NotActions  DataActions NotDataActions
-------     ----------  ----------- --------------
0 action(s) 0 action(s) 3 action(s) 0 action(s)

PS C:\> $backupRole.Permissions.DataActions

Microsoft.KeyVault/managedHsm/backup/start/action
Microsoft.KeyVault/managedHsm/backup/status/action
Microsoft.KeyVault/managedHsm/keys/backup/action
```


## <a name="azmanagedservices"></a>Az.ManagedServices

### `New-AzManagedServicesDefinition`
Parameter `-DisplayName` telah dihapus.

#### <a name="before"></a>Sebelum
```powershell
PS C:\> New-AzManagedServicesDefinition -DisplayName "MyTestDefinition" -ManagedByTenantId 72f9acbf-86f1-41af-91ab-2d7ef011db47 -RoleDefinitionId acdd72a7-3385-48ef-bd42-f606fba81ae7 -PrincipalId 714160ec-87d5-42bb-8b17-287c0dd7417d
```
#### <a name="after"></a>Setelah
```powershell
PS C:\> $permantAuth = New-AzManagedServicesAuthorizationObject -PrincipalId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -RoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -PrincipalIdDisplayName "Test user" -DelegatedRoleDefinitionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx","xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
PS C:\> New-AzManagedServicesDefinition -Name xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx -RegistrationDefinitionName "Test definition" -ManagedByTenantId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -Authorization $permantAuth -Description "Test definition desc" -Scope "/subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
```


## <a name="azmonitor"></a>Az.Monitor

### `Get-AzLog`

Tipe properti 'Nama EventName', 'Kategori', 'ResourceProviderName', 'OperationName', 'Status', 'SubStatus telah diubah `Microsoft.Azure.Management.Monitor.Models.LocalizableString` dari menjadi `System.String`

#### <a name="before"></a>Sebelum
```powershell
PS C:\> $log = Get-AzLog -MaxRecord 1
PS C:\> $eventName = $log.EventName.LocalizedValue
PS C:\> $category = $log.Category.LocalizedValue
PS C:\> $resourceProviderName = $log.ResourceProviderName.LocalizedValue
PS C:\> $operationName = $log.OperationName.LocalizedValue
PS C:\> $status = $log.Status.LocalizedValue
PS C:\> $subStatus = $log.SubStatus.LocalizedValue
```
#### <a name="after"></a>Setelah
```powershell
PS C:\> $log = Get-AzLog -MaxRecord 1
PS C:\> $eventName = $log.EventName
PS C:\> $category = $log.Category
PS C:\> $resourceProviderName = $log.ResourceProviderName
PS C:\> $operationName = $log.OperationName
PS C:\> $status = $log.Status
PS C:\> $subStatus = $log.SubStatus
```


### `Get-AzMetric,Get-AzMetricDefinition`
Tipe properti 'Unit' telah diubah menjadi `System.String`

```
There is no change to the usage.
```



### `New-AzMetricAlertRuleV2Criteria`
Tipe properti 'Agregasi Waktu' telah diubah menjadi `System.String`

```
There is no change to the usage.
```



## <a name="azoperationalinsights"></a>Az.OperationalInsights

### `Get-AzOperationalInsightsCluster`
Membuat "daftar" kumpulan parameter default.

#### <a name="before"></a>Sebelum
```powershell
There is no default parameter set.
```
#### <a name="after"></a>Setelah
```powershell
Default parameter set is now "list", when providing resource group name - return all clusters for the given resource group.
```


### `Update-AzOperationalInsightsCluster`
Membuat "UpdateByNameParameterSet" kumpulan parameter default.

#### <a name="before"></a>Sebelum
```powershell
There is no default parameter set.
```
#### <a name="after"></a>Setelah
```powershell
Default parameter set is now "UpdateByNameParameterSet".
```


## <a name="azrecoveryservices"></a>Az.RecoveryServices

### `Get-AzRecoveryServicesBackupContainer`
Mengubah BackupManagementType dari MARS menjadi MAB. Fungsi tetap sama, hal ini dilakukan untuk menghadirkan konsistensi di seluruh cmdlet.

#### <a name="before"></a>Sebelum
```powershell
$containers = Get-AzRecoveryServicesBackupContainer -ContainerType Windows -BackupManagementType MARS -VaultId $vault.ID
```
#### <a name="after"></a>Setelah
```powershell
$cont = Get-AzRecoveryServicesBackupContainer -ContainerType Windows -BackupManagementType MAB -VaultId $vault.ID
```


### `Get-AzRecoveryServicesBackupItem`
Mengubah BackupManagementType dari MARS menjadi MAB. Fungsi tetap sama, hal ini dilakukan untuk menghadirkan konsistensi di seluruh cmdlet

#### <a name="before"></a>Sebelum
```powershell
Get-AzRecoveryServicesBackupItem -BackupManagementType MARS -VaultId $vault.ID -WorkloadType FileFolder
```
#### <a name="after"></a>Setelah
```powershell
Get-AzRecoveryServicesBackupItem -BackupManagementType MAB -VaultId $vault.ID -WorkloadType FileFolder
```


### `Get-AzRecoveryServicesBackupJob`
Mengubah BackupManagementType dari MARS menjadi MAB. Fungsi tetap sama, hal ini dilakukan untuk menghadirkan konsistensi di seluruh cmdlet

#### <a name="before"></a>Sebelum
```powershell
Get-AzRecoveryServicesBackupJob -BackupManagementType MARS -VaultId $vault.ID
```
#### <a name="after"></a>Setelah
```powershell
Get-AzRecoveryServicesBackupJob -BackupManagementType MAB -VaultId $vault.ID
```


## <a name="azresources"></a>Az.Resources

### `AzAD cmdlets`
Silakan lihat [panduan migrasi](/powershell/azure/azps-msgraph-migration-changes) cmdlet Active Directory.

### `PolicyAssignment cmdlets`
Tipe 'Identitas' properti dari tipe 'Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyAssignment' telah berubah dari 'System.Management.Automation.PSObject' menjadi 'Microsoft.Azure.Commands.ResourceManager.Cmdlets.Implementation.Policy.PsPolicyIdentity'.

#### <a name="before"></a>Sebelum
```powershell
PS C:\> $v = Get-AzPolicyAssignment -Id $someId
PS C:\> Write-Host $v.type, $v.principalId, $v.tenantId
```
#### <a name="after"></a>Setelah
```powershell
PS C:\> $v = Get-AzPolicyAssignment -Id $someId
PS C:\> Write-Host $v.IdentityType, $v.PrincipalId, $v.TenantId, $v.UserAssignedIdentities
```


## <a name="azstorage"></a>Az.Storage

### `Get-AzRmStorageShare`
Parameter "Name" telah dihapus dari parameter set "ShareResourceId", karena nama dapat disimpulkan dari ID sumber daya.

#### <a name="before"></a>Sebelum
```powershell
$StorageShare = Get-AzRmStorageShare -ResourceId "/subscriptions/..." -Name "MyStorageShare"
```
#### <a name="after"></a>Setelah
```powershell
$StorageShare = Get-AzRmStorageShare -ResourceId "/subscriptions/..."
```
