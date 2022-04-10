---
description: Panduan migrasi ini berisi daftar perubahan berisiko yang dibuat untuk Azure PowerShell dalam rilis Az versi 5.0.0.
ms.custom: devx-track-azurepowershell
ms.date: 03/12/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Panduan migrasi untuk Az 5.0.0
ms.openlocfilehash: 6e9e0f10285a8a7e3c6cf68bcd64a41e19eab5c8
ms.sourcegitcommit: b346b2fbd8b25f54759984e75ddbee3304921c43
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/16/2022
ms.locfileid: "140663553"
---
# <a name="migration-guide-for-az-500"></a>Panduan Migrasi untuk Az 5.0.0

Dokumen ini menjelaskan perubahan antara Az versi 4.0.0 dan 5.0.0.

- [Panduan Migrasi untuk Az 5.0.0](#migration-guide-for-az-500)
  - [Az.Aks](#azaks)
    - [New-AzAksCluster](#new-azakscluster)
    - [Set-AzAksCluster](#set-azakscluster)
  - [Az.ContainerRegistry](#azcontainerregistry)
    - [New-AzContainerRegistry](#new-azcontainerregistry)
  - [Az.Functions](#azfunctions)
    - [Get-AzFunctionApp](#get-azfunctionapp)
    - [New-AzFunctionApp](#new-azfunctionapp)
  - [Az.KeyVault](#azkeyvault)
    - [New-AzKeyVault](#new-azkeyvault)
    - [Update-AzKeyVault](#update-azkeyvault)
    - [Get-AzKeyVaultSecret](#get-azkeyvaultsecret)
  - [Az.ManagedServices](#azmanagedservices)
    - [Get-AzManagedServicesDefinition](#get-azmanagedservicesdefinition)
    - [New-AzManagedServicesAssignment](#new-azmanagedservicesassignment)
    - [Remove-AzManagedServicesAssignment](#remove-azmanagedservicesassignment)
    - [Remove-AzManagedServicesDefinition](#remove-azmanagedservicesdefinition)
  - [Az.ResourceManager](#azresourcemanager)
    - [Get-AzManagementGroupDeployment](#get-azmanagementgroupdeployment)
    - [Get-AzManagementGroupDeploymentOperation](#get-azmanagementgroupdeploymentoperation)
    - [Get-AzDeployment](#get-azdeployment)
    - [Get-AzDeploymentOperation](#get-azdeploymentoperation)
    - [Get-AzDeploymentWhatIfResult](#get-azdeploymentwhatifresult)
    - [Get-AzTenantDeployment](#get-aztenantdeployment)
    - [Get-AzTenantDeploymentOperation](#get-aztenantdeploymentoperation)
    - [New-AzManagementGroupDeployment](#new-azmanagementgroupdeployment)
    - [New-AzDeployment](#new-azdeployment)
    - [New-AzTenantDeployment](#new-aztenantdeployment)
    - [Remove-AzManagementGroupDeployment](#remove-azmanagementgroupdeployment)
    - [Remove-AzDeployment](#remove-azdeployment)
    - [Remove-AzTenantDeployment](#remove-aztenantdeployment)
    - [Save-AzManagementGroupDeploymentTemplate](#save-azmanagementgroupdeploymenttemplate)
    - [Save-AzDeploymentTemplate](#save-azdeploymenttemplate)
    - [Save-AzTenantDeploymentTemplate](#save-aztenantdeploymenttemplate)
    - [Stop-AzManagementGroupDeployment](#stop-azmanagementgroupdeployment)
    - [Stop-AzDeployment](#stop-azdeployment)
    - [Stop-AzTenantDeployment](#stop-aztenantdeployment)
    - [Test-AzManagementGroupDeployment](#test-azmanagementgroupdeployment)
    - [Test-AzDeployment](#test-azdeployment)
    - [Test-AzTenantDeployment](#test-aztenantdeployment)
    - [Get-AzResourceGroupDeployment](#get-azresourcegroupdeployment)
    - [Get-AzResourceGroupDeploymentOperation](#get-azresourcegroupdeploymentoperation)
    - [Get-AzResourceGroupDeploymentWhatIfResult](#get-azresourcegroupdeploymentwhatifresult)
    - [New-AzResourceGroupDeployment](#new-azresourcegroupdeployment)
    - [Remove-AzResourceGroupDeployment](#remove-azresourcegroupdeployment)
    - [Save-AzResourceGroupDeploymentTemplate](#save-azresourcegroupdeploymenttemplate)
    - [Stop-AzResourceGroupDeployment](#stop-azresourcegroupdeployment)
    - [Test-AzResourceGroupDeployment](#test-azresourcegroupdeployment)
    - [Get-AzManagementGroupDeploymentWhatIfResult](#get-azmanagementgroupdeploymentwhatifresult)
    - [Get-AzTenantDeploymentWhatIfResult](#get-aztenantdeploymentwhatifresult)
  - [Az.Sql](#azsql)
    - [Set-AzSqlServerActiveDirectoryAdministrator](#set-azsqlserveractivedirectoryadministrator)
  - [Az.Synapse](#azsynapse)
    - [New-AzSynapseSqlPool](#new-azsynapsesqlpool)
    - [Update-AzSynapseSqlPool](#update-azsynapsesqlpool)
  - [Az.Network](#aznetwork)
    - [Approve-AzPrivateEndpointConnection](#approve-azprivateendpointconnection)
    - [Deny-AzPrivateEndpointConnection](#deny-azprivateendpointconnection)
    - [Get-AzPrivateEndpointConnection](#get-azprivateendpointconnection)
    - [Remove-AzPrivateEndpointConnection](#remove-azprivateendpointconnection)
    - [Set-AzPrivateEndpointConnection](#set-azprivateendpointconnection)
    - [New-AzNetworkWatcherConnectionMonitorEndpointObject](#new-aznetworkwatcherconnectionmonitorendpointobject)

## <a name="azaks"></a>Az.Aks

### <a name="new-azakscluster"></a>New-AzAksCluster

- Tidak lagi mendukung parameter `NodeOsType` dan tidak ada alias yang ditemukan untuk nama parameter asli, parameter akan selalu berupa `Linux`.
- Tidak lagi mendukung alias `ClientIdAndSecret` untuk parameter `ServicePrincipalIdAndSecret`.
- Nilai default `NodeVmSetType` diubah dari `AvailabilitySet` menjadi `VirtualMachineScaleSets`.
- Nilai default `NetworkPlugin` diubah dari `none` menjadi `azure`.

#### <a name="before"></a>Sebelumnya

```powershell
New-AzAksCluster -ResourceGroupName myResourceGroup -Name myCluster -WindowsProfileAdminUserName azureuser -WindowsProfileAdminUserPassword $cred -NetworkPlugin azure -NodeOsType Linux -ClientIdAndSecret xxx
```

#### <a name="after"></a>Sesudahnya

```powershell
New-AzAksCluster -ResourceGroupName myResourceGroup -Name myCluster -WindowsProfileAdminUserName azureuser -WindowsProfileAdminUserPassword $cred -NodeVmSetType AvailabilitySet  -ServicePrincipalIdAndSecret xxx
```

### <a name="set-azakscluster"></a>Set-AzAksCluster

Tidak lagi mendukung alias `ClientIdAndSecret` untuk parameter `ServicePrincipalIdAndSecret`.

#### <a name="before"></a>Sebelumnya

```powershell
Get-AzAksCluster -ResourceGroupName xxx -Name xxx | Set-AzAksCluster -ClientIdAndSecret xxx
```

#### <a name="after"></a>Sesudahnya

```powershell
Get-AzAksCluster -ResourceGroupName xxx -Name xxx | Set-AzAksCluster -ServicePrincipalIdAndSecret xxx
```

## <a name="azcontainerregistry"></a>Az.ContainerRegistry

### <a name="new-azcontainerregistry"></a>New-AzContainerRegistry

Tidak lagi mendukung parameter `StorageAccountName` dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelumnya

```powershell
New-AzContainerRegistry -Name $name -ResourceGroupName $rg -Location $location -SKU Classic -StorageAccountName $storage
```

#### <a name="after"></a>Sesudahnya

`Classic` tidak digunakan lagi dan `StorageAccountName` dihapus karena hanya berfungsi dengan Classic Container Registry.

## <a name="azfunctions"></a>Az.Functions

### <a name="get-azfunctionapp"></a>Get-AzFunctionApp

Menghapus parameter switch `IncludeSlot` dari semua, kecuali satu set parameter dari `Get-AzFunctionApp`. Cmdlet sekarang mendukung pengambilan slot penyebaran dalam hasil saat `-IncludeSlot` ditentukan.
Fungsi ini bermasalah di versi cmdlet sebelumnya. Namun, kini telah diperbaiki.

### <a name="new-azfunctionapp"></a>New-AzFunctionApp

- Memperbaiki `-DisableApplicationInsights` di `New-AzFunctionApp` sehingga tidak ada proyek Application Insights yang dibuat ketika opsi ini ditentukan.
- Menghapus dukungan untuk membuat aplikasi fungsi PowerShell 6.2 karena PowerShell 6.2 adalah EOL. Panduan saat ini untuk pelanggan adalah membuat aplikasi fungsi PowerShell 7.0 sebagai gantinya.
- Mengubah versi runtime default dalam Functions versi 3 di Windows untuk aplikasi fungsi PowerShell dari 6.2 hingga 7.0 saat parameter `RuntimeVersion` tidak ditentukan.
- Mengubah versi runtime default dalam Functions versi 3 di Windows dan Linux untuk aplikasi fungsi Node dari 10 hingga 12 saat parameter `RuntimeVersion` tidak ditentukan. Namun, pengguna tetap dapat membuat aplikasi fungsi Node 10 dengan menentukan `-Runtime Node` dan `-RuntimeVersion 10`. Mengubah versi runtime default dalam Functions versi 3 di Linux untuk aplikasi fungsi Python dari 3.7 hingga 3.8 saat parameter `RuntimeVersion` tidak ditentukan. Namun, pengguna tetap dapat membuat aplikasi fungsi Python 3.7 dengan menentukan `-Runtime Python` dan `-RuntimeVersion 3.7`.

#### <a name="before"></a>Sebelumnya

```powershell
# Create a Node 10 function app on Linux
New-AzFunctionApp -ResourceGroupName $rd `
                  -Name $functionAppName `
                  -StorageAccountName $storageAccountName `
                  -Location $location `
                  -OSType Linux `
                  -Runtime Node

# Create a Node 10 function app on Windows
New-AzFunctionApp -ResourceGroupName $rd `
                  -Name $functionAppName `
                  -StorageAccountName $storageAccountName `
                  -Location $location `
                  -OSType Windows `
                  -Runtime Node

# Create a Python 3.7 function app on Linux
New-AzFunctionApp -ResourceGroupName $rd `
                  -Name $functionAppName `
                  -StorageAccountName $storageAccountName `
                  -Location $location `
                  -OSType Linux `
                  -Runtime Python
```

#### <a name="after"></a>Sesudahnya

```powershell
# Create a Node 10 function app on Linux
New-AzFunctionApp -ResourceGroupName $rd `
                  -Name $functionAppName `
                  -StorageAccountName $storageAccountName `
                  -Location $location `
                  -OSType Linux `
                  -Runtime Node `
                  -RuntimeVersion 10

# Create a Node 10 function app on Windows
New-AzFunctionApp -ResourceGroupName $rd `
                  -Name $functionAppName `
                  -StorageAccountName $storageAccountName `
                  -Location $location `
                  -OSType Windows `
                  -Runtime Node

# Create a Python 3.7 function app on Linux
New-AzFunctionApp -ResourceGroupName $rd `
                  -Name $functionAppName `
                  -StorageAccountName $storageAccountName `
                  -Location $location `
                  -OSType Linux `
                  -Runtime Python `
                  -RuntimeVersion 3.7
```

## <a name="azkeyvault"></a>Az.KeyVault

### <a name="new-azkeyvault"></a>New-AzKeyVault

Tidak lagi mendukung parameter `DisableSoftDelete` dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelumnya

```powershell
# Opt out soft delete while creating a key vault
New-AzKeyVault -VaultName 'Contoso03Vault' -ResourceGroupName 'Group14' -Location 'East US' -DisableSoftDelete
```

#### <a name="after"></a>Sesudahnya

Kemampuan untuk memperbarui pengaturan penghapusan sementara tidak digunakan lagi di Az.KeyVault 3.0.0. [Baca selengkapnya](/azure/key-vault/general/soft-delete-change)

### <a name="update-azkeyvault"></a>Update-AzKeyVault

Tidak lagi mendukung parameter `EnableSoftDelete`, `SoftDeleteRetentionInDays`, dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelumnya

```powershell
Update-AzKeyVault -VaultName 'Contoso03Vault' -ResourceGroupName 'Group14' -EnableSoftDelete -SoftDeleteRetentionInDays 15
```

#### <a name="after"></a>Sesudahnya

Kemampuan untuk memperbarui pengaturan penghapusan sementara tidak digunakan lagi di Az.KeyVault 3.0.0. [Baca selengkapnya](/azure/key-vault/general/soft-delete-change)

### <a name="get-azkeyvaultsecret"></a>Get-AzKeyVaultSecret

Properti `SecretValueText` jenis `Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultSecret` telah dihapus. Terapkan `-AsPlainText` pada panggilan untuk mendapatkan rahasia teks biasa, atau gunakan `$secret.SecretValue` jenis `SecureString` di skrip Anda.

#### <a name="before"></a>Sebelumnya

```powershell
$secret = Get-AzKeyVaultSecret -VaultName myVault -Name mySecret
$secretInPlainText = $secret.SecretValueText
```

#### <a name="after"></a>Sesudahnya

```powershell
$secretInPlainText = Get-AzKeyVaultSecret -VaultName myVault -Name mySecret -AsPlainText
```

## <a name="azmanagedservices"></a>Az.ManagedServices

### <a name="get-azmanagedservicesdefinition"></a>Get-AzManagedServicesDefinition

Tidak lagi mendukung parameter `ResourceId` dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelumnya

```powershell
Get-AzManagedServicesDefinition -ResourceId xxx
```

#### <a name="after"></a>Sesudahnya

```powershell
Get-AzManagedServicesDefinition -Id xxx
```

### <a name="new-azmanagedservicesassignment"></a>New-AzManagedServicesAssignment

Tidak lagi mendukung parameter `RegistrationDefinitionName`, `RegistrationDefinitionResourceId`, dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelumnya

```powershell
New-AzManagedServicesAssignment -RegistrationDefinitionName xxx -Scope xxx
```

#### <a name="after"></a>Sesudahnya

```powershell
New-AzManagedServicesAssignment -Scope xxx -RegistrationDefinition xxx
```

### <a name="remove-azmanagedservicesassignment"></a>Remove-AzManagedServicesAssignment

Tidak lagi mendukung parameter `Id`, `ResourceId`, dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelumnya

```powershell
Remove-AzManagedServicesAssignment -ResourceId xxx
```

#### <a name="after"></a>Sesudahnya

```powershell
Get-AzManagedServicesAssignment -Scope xxx | Remove-AzManagedServicesAssignment
```

### <a name="remove-azmanagedservicesdefinition"></a>Remove-AzManagedServicesDefinition

Tidak lagi mendukung parameter `Id`, `ResourceId`, dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelumnya

```powershell
Remove-AzManagedServicesDefinition -ResourceId xxx
```

#### <a name="after"></a>Sesudahnya

```powershell
Get-AzManagedServicesDefinition -Scope xxx | Remove-AzManagedServicesDefinition
```

## <a name="azresourcemanager"></a>Az.ResourceManager

### <a name="get-azmanagementgroupdeployment"></a>Get-AzManagementGroupDeployment

Tidak lagi mendukung parameter `ApiVersion` dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelumnya

```powershell
Get-AzManagementGroupDeployment -ManagementGroupId xxx -Name xxx -ApiVersion xxx
```

#### <a name="after"></a>Sesudahnya

```powershell
Get-AzManagementGroupDeployment -ManagementGroupId xxx -Name xxx
```

### <a name="get-azmanagementgroupdeploymentoperation"></a>Get-AzManagementGroupDeploymentOperation

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="get-azdeployment"></a>Get-AzDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="get-azdeploymentoperation"></a>Get-AzDeploymentOperation

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="get-azdeploymentwhatifresult"></a>Get-AzDeploymentWhatIfResult

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="get-aztenantdeployment"></a>Get-AzTenantDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="get-aztenantdeploymentoperation"></a>Get-AzTenantDeploymentOperation

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="new-azmanagementgroupdeployment"></a>New-AzManagementGroupDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="new-azdeployment"></a>New-AzDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="new-aztenantdeployment"></a>New-AzTenantDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="remove-azmanagementgroupdeployment"></a>Remove-AzManagementGroupDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="remove-azdeployment"></a>Remove-AzDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="remove-aztenantdeployment"></a>Remove-AzTenantDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="save-azmanagementgroupdeploymenttemplate"></a>Save-AzManagementGroupDeploymentTemplate

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="save-azdeploymenttemplate"></a>Save-AzDeploymentTemplate

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="save-aztenantdeploymenttemplate"></a>Save-AzTenantDeploymentTemplate

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="stop-azmanagementgroupdeployment"></a>Stop-AzManagementGroupDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="stop-azdeployment"></a>Stop-AzDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="stop-aztenantdeployment"></a>Stop-AzTenantDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="test-azmanagementgroupdeployment"></a>Test-AzManagementGroupDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="test-azdeployment"></a>Test-AzDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="test-aztenantdeployment"></a>Test-AzTenantDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="get-azresourcegroupdeployment"></a>Get-AzResourceGroupDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="get-azresourcegroupdeploymentoperation"></a>Get-AzResourceGroupDeploymentOperation

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="get-azresourcegroupdeploymentwhatifresult"></a>Get-AzResourceGroupDeploymentWhatIfResult

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="new-azresourcegroupdeployment"></a>New-AzResourceGroupDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="remove-azresourcegroupdeployment"></a>Remove-AzResourceGroupDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="save-azresourcegroupdeploymenttemplate"></a>Save-AzResourceGroupDeploymentTemplate

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="stop-azresourcegroupdeployment"></a>Stop-AzResourceGroupDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="test-azresourcegroupdeployment"></a>Test-AzResourceGroupDeployment

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="get-azmanagementgroupdeploymentwhatifresult"></a>Get-AzManagementGroupDeploymentWhatIfResult

Sama halnya dengan `Get-AzManagementGroupDeployment`.

### <a name="get-aztenantdeploymentwhatifresult"></a>Get-AzTenantDeploymentWhatIfResult

Sama halnya dengan `Get-AzManagementGroupDeployment`.

## <a name="azsql"></a>Az.Sql

### <a name="set-azsqlserveractivedirectoryadministrator"></a>Set-AzSqlServerActiveDirectoryAdministrator

Tidak lagi mendukung parameter `IsAzureADOnlyAuthentication` dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelumnya

```powershell
Set-AzSqlServerActiveDirectoryAdministrator -ResourceGroupName 'ResourceGroup01' -ServerName 'Server01' -DisplayName 'DBAs' -IsAzureADOnlyAuthentication
```

#### <a name="after"></a>Sesudahnya

```powershell
Set-AzSqlServerActiveDirectoryAdministrator -ResourceGroupName 'ResourceGroup01' -ServerName 'Server01' -DisplayName 'DBAs'
```

## <a name="azsynapse"></a>Az.Synapse

### <a name="new-azsynapsesqlpool"></a>New-AzSynapseSqlPool

Tidak lagi mendukung parameter `FromBackup`, `FromRestorePoint`, `BackupResourceGroupName`, `BackupWorkspaceName`, `BackupSqlPoolName`, `BackupSqlPoolObject`, `BackupResourceId`, `SourceResourceGroupName`, `SourceWorkspaceName`, `SourceSqlPoolName`, `SourceSqlPoolObject`, `SourceResourceId`, `RestorePoint`, dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelumnya

```powershell
New-AzSynapseSqlPool -FromBackup -WorkspaceName ContosoWorkspace -Name ContosoSqlPool -BackupWorkspaceName ContosoWorkspace -BackupSqlPoolName ExistingContosoSqlPool
```

#### <a name="after"></a>Sesudahnya

```powershell
PS C:\> New-AzSynapseSqlPool -WorkspaceName ContosoWorkspace -Name ContosoSqlPool -PerformanceLevel DW200c
```

### <a name="update-azsynapsesqlpool"></a>Update-AzSynapseSqlPool

Tidak lagi mendukung parameter `Suspend`, `Resume`, dan tidak ada alias yang ditemukan untuk nama parameter asli.

## <a name="aznetwork"></a>Az.Network

### <a name="approve-azprivateendpointconnection"></a>Approve-AzPrivateEndpointConnection

Tidak lagi mendukung parameter `PrivateLinkResourceType` dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelumnya

```powershell
Approve-AzPrivateEndpointConnection -ResourceGroupName xxx -ServiceName xxx -Name xxx -PrivateLinkResourceType 'Microsoft.Network/privateLinkServices' -Description xxx
```

#### <a name="after"></a>Sesudahnya

```powershell
Approve-AzPrivateEndpointConnection -ResourceGroupName xxx -ServiceName xxx -Name xxx -Description xxx
```

### <a name="deny-azprivateendpointconnection"></a>Deny-AzPrivateEndpointConnection

Sama halnya dengan `Approve-AzPrivateEndpointConnection`.

### <a name="get-azprivateendpointconnection"></a>Get-AzPrivateEndpointConnection

Sama halnya dengan `Approve-AzPrivateEndpointConnection`.

### <a name="remove-azprivateendpointconnection"></a>Remove-AzPrivateEndpointConnection

Sama halnya dengan `Approve-AzPrivateEndpointConnection`.

### <a name="set-azprivateendpointconnection"></a>Set-AzPrivateEndpointConnection

Sama halnya dengan `Approve-AzPrivateEndpointConnection`.

### <a name="new-aznetworkwatcherconnectionmonitorendpointobject"></a>New-AzNetworkWatcherConnectionMonitorEndpointObject

Tidak lagi mendukung parameter `FilterType`, `FilterItem`, dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelumnya

```powershell
$MySrcResourceId1 = '/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/myresourceGroup/providers/Microsoft.OperationalInsights/workspaces/myworkspace'
$SrcEndpointFilterItem1 =New-AzNetworkWatcherConnectionMonitorEndpointFilterItemObject -Type 'AgentAddress' -Address 'WIN-P0HGNDO2S1B'
$SourceEndpointObject1 = New-AzNetworkWatcherConnectionMonitorEndPointObject -Name 'workspaceEndpoint' -ResourceId $MySrcResourceId1 -FilterType Include -FilterItem $SrcEndpointFilterItem1
```

#### <a name="after"></a>Sesudahnya

```powershell
MySrcResourceId1 = '/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/myresourceGroup/providers/Microsoft.OperationalInsights/workspaces/myworkspace'
$SourceEndpointObject1 = New-AzNetworkWatcherConnectionMonitorEndPointObject -Name 'workspaceEndpoint' -ResourceId $MySrcResourceId1
```
