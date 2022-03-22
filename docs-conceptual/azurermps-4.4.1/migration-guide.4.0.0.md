---
title: Perubahan breaking untuk Microsoft Azure PowerShell 4.0.0
description: Panduan migrasi ini berisi daftar perubahan melanggar yang dibuat untuk Azure PowerShell dalam rilis versi 4.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/01/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 3e5be2d8279b28e683fbe8a03b812c658fcecf33
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427988"
---
# <a name="breaking-changes-for-microsoft-azure-powershell-400"></a>Perubahan breaking untuk Microsoft Azure PowerShell 4.0.0

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Dokumen ini berfungsi sebagai pemberitahuan perubahan dan panduan migrasi bagi konsumen cmdlet Microsoft Azure PowerShell. Setiap bagian menggambarkan dorongan untuk perubahan yang melanggar dan jalur migrasi resistensi paling sedikit. Untuk konteks mendalam, silakan lihat permintaan pull yang terkait dengan setiap perubahan.

## <a name="table-of-contents"></a>Daftar Isi

- [Perubahan yang melanggar ke cmdlet Compute](#breaking-changes-to-compute-cmdlets)
- [Perubahan yang melanggar ke cmdlet EventHub](#breaking-changes-to-eventhub-cmdlets)
- [Perubahan yang melanggar ke cmdlet Insights](#breaking-changes-to-insights-cmdlets)
- [Perubahan yang melanggar ke cmdlet Network](#breaking-changes-to-network-cmdlets)
- [Perubahan yang melanggar ke cmdlet ServiceBus](#breaking-changes-to-servicebus-cmdlets)
- [Perubahan yang melanggar ke cmdlet Sql](#breaking-changes-to-sql-cmdlets)
- [Perubahan yang melanggar ke cmdlet Storage](#breaking-changes-to-storage-cmdlets)
- [Perubahan yang melanggar ke cmdlet Profile](#breaking-changes-to-profile-cmdlets)
  ## <a name="breaking-changes-to-compute-cmdlets"></a>Perubahan yang melanggar ke cmdlet Compute

Jenis output berikut terpengaruh rilis ini:

### <a name="psvirtualmachine"></a>PSVirtualMachine
- Properti tingkat atas `DataDiskNames` dan `NetworkInterfaceIDs` dari objek `PSVirtualMachine` telah dihapus dari jenis output. Properti ini selalu tersedia di properti `StorageProfile` dan `NetworkProfile` dari objek `PSVirtualMachine` dan akan menjadi cara mengaksesnya ke depan.
- Perubahan ini memengaruhi cmdlet berikut:
    - `Add-AzureRmVMDataDisk`
    - `Add-AzureRmVMNetworkInterface`
    - `Get-AzureRmVM`
    - `Remove-AzureRmVMDataDisk`
    - `Remove-AzureRmVMNetworkInterface`
    - `Set-AzureRmVMDataDisk`

```powershell-interactive
# Old
$vm.DataDiskNames
$vm.NetworkInterfaceIDs

# New
$vm.StorageProfile.DataDisks | Select -Property Name
$vm.NetworkProfile.NetworkInterfaces | Select -Property Id
```

## <a name="breaking-changes-to-eventhub-cmdlets"></a>Perubahan yang melanggar ke cmdlet EventHub

Cmdlet berikut terpengaruh rilis ini:

### <a name="get-azurermeventhubnamespace"></a>Get-AzureRmEventHubNamespace
- Properti `ResourceGroupName` telah dihapus dari jenis output `NamespaceAttributes`

### <a name="new-azurermeventhubnamespace"></a>New-AzureRmEventHubNamespace
- Properti `ResourceGroupName` telah dihapus dari jenis output `NamespaceAttributes`

## <a name="breaking-changes-to-insights-cmdlets"></a>Perubahan yang melanggar ke cmdlet Insights

Cmdlet berikut terpengaruh rilis ini:

### <a name="get-azurermusage"></a>Get-AzureRmUsage
- Cmdlet ini tidak digunakan lagi.

### <a name="remove-azurermalertrule"></a>Remove-AzureRmAlertRule
- Output cmdlet ini telah berubah dari daftar dengan satu objek menjadi satu objek; objek ini mencakup requestId, dan kode status.

```powershell-interactive
# Old
$s1 = Remove-AzureRmAlertRule -ResourceGroup $resourceGroup -name chiricutin
if ($s1 -ne $null)
{
    $r = $s1(0).RequestId
    $s = $s1(0).StatusCode
}

# New
$s1 = Remove-AzureRmAlertRule -ResourceGroup $resourceGroup -name chiricutin
$r = $s1.RequestId
$s = $s1.StatusCode
```

### <a name="add-azurermlogalertrule"></a>Add-AzureRmLogAlertRule
- Cmdlet ini tidak digunakan lagi.

### <a name="get-azurermalertrule"></a>Get-AzureRmAlertRule
- Setiap elemen output (daftar objek) dari cmdlet ini diratakan, yaitu sebagai ganti mengembalikan objek dengan struktur `{ Id, Location, Name, Tags, Properties }`, ini akan mengembalikan objek dengan struktur `{ Id, Location, Name, Tags, Type, Description, IsEnabled, Condition, Actions, LastUpdatedTime, ...}`, yang semuanya merupakan atribut Sumber Daya Azure ditambah semua atribut AlertRuleResource di tingkat atas.

```powershell-interactive
# Old
$rules = Get-AzureRmAlertRule -ResourceGroup $resourceGroup
if ($rules -and $rules.count -ge 1)
{
    Write-Host -fore red "Error updating alert rule"

    Write-Host $rules(0).Id
    Write-Host $rules(0).Properties.IsEnabled
    Write-Host $rules(0).Properties.Condition
}

# New
$rules = Get-AzureRmAlertRule -ResourceGroup $resourceGroup
if ($rules -and $rules.count -ge 1)
{
    Write-Host -fore red "Error updating alert rule"

    Write-Host $rules(0).Id

    # Properties will remain for a while
    Write-Host $rules(0).Properties.IsEnabled

    # But the properties will be at the top level too. Later Properties will be removed
    Write-Host $rules(0).IsEnabled
    Write-Host $rules(0).Condition
}
```

### <a name="get-azurermautoscalesetting"></a>Get-AzureRmAutoscaleSetting
- Bidang `AutoscaleSettingResourceName` tidak digunakan lagi karena selalu memiliki nilai yang sama dengan bidang `Name`.

```powershell-interactive
# Old
$s1 = Get-AzureRmAutoscaleSetting -ResourceGroup $resourceGroup -Name MySetting
if ($s1.AutoscaleSettingResourceName -ne $s1.Name)
{
    Write-Host "There is something wrong with the name"
}

# New
$s1 = Get-AzureRmAutoscaleSetting -ResourceGroup $resourceGroup -Name MySetting

# There won't be a AutoscaleSettingResourceName
Write-Host $s1.Name
```

### <a name="remove-azurermlogprofile"></a>Remove-AzureRmLogProfile
- Output dari cmdlet ini akan berubah dari `Boolean` ke dan objek yang berisi `RequestId` dan `StatusCode`

```powershell-interactive
# Old
$s1 = Remove-AzureRmLogProfile -Name myLogProfile
if ($s1 -eq $true)
{
    Write-Host "Removed"
}
else
{
    Write-Host "Failed"
}

# New
$s1 = Remove-AzureRmLogProfile -Name myLogProfile
$r = $s1.RequestId
$s = $s1.StatusCode
```

### <a name="add-azurermlogprofile"></a>Add-AzureRmLogProfile
- Output cmdlet ini akan berubah dari objek yang mencakup requestId, kode status, dan sumber daya yang diperbarui atau baru dibuat

```powershell-interactive
# Old
$s1 = Add-AzureRmLogProfile -Name default -StorageAccountId /subscriptions/df602c9c-7aa0-407d-a6fb-eb20c8bd1192/resourceGroups/JohnKemTest/providers/Microsoft.Storage/storageAccounts/johnkemtest8162 -Locations Global -categ Delete, Write, Action -retention 3
$r = $s1.ServiceBusRuleId

# New
$s1 = Add-AzureRmLogProfile -Name default -StorageAccountId /subscriptions/df602c9c-7aa0-407d-a6fb-eb20c8bd1192/resourceGroups/JohnKemTest/providers/Microsoft.Storage/storageAccounts/johnkemtest8162 -Locations Global -categ Delete, Write, Action -retention 3
$r = $s1.RequestId
$s = $s1.StatusCode
$a = $s1.NewResource.ServiceBusRuleId

```

### <a name="set-azurermdiagnosticsettings"></a>Set-AzureRmDiagnosticSettings
- Perintah ini akan berganti nama menjadi `Update-AzureRmDiagnosticSettings`

```powershell-interactive
# Old
Set-AzureRmDiagnosticSettings

# New
Update-AzureRmDiagnosticSettings
```

## <a name="breaking-changes-to-network-cmdlets"></a>Perubahan yang melanggar ke cmdlet Network

Cmdlet berikut terpengaruh rilis ini:

### <a name="new-azurermvirtualnetworkgatewayconnection"></a>New-AzureRmVirtualNetworkGatewayConnection
- Parameter `EnableBgp` telah diubah untuk mengambil `boolean` sebagai ganti `string`

```powershell-interactive
# Old
New-AzureRmVirtualNetworkGatewayConnection -ResourceGroupName "RG" -name "conn1" -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localnetGateway -ConnectionType IPsec -SharedKey "key" -EnableBgp "true"

# New
New-AzureRmVirtualNetworkGatewayConnection -ResourceGroupName "RG" -name "conn1" -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localnetGateway -ConnectionType IPsec -SharedKey "key" -EnableBgp $true
```

## <a name="breaking-changes-to-servicebus-cmdlets"></a>Perubahan yang melanggar ke cmdlet ServiceBus

Cmdlet berikut terpengaruh rilis ini:

### <a name="get-azurermservicebusnamespace"></a>Get-AzureRmServiceBusNamespace
- Properti `ResourceGroupName` telah dihapus dari jenis output `NamespaceAttributes`

### <a name="new-azurermservicebusnamespace"></a>New-AzureRmServiceBusNamespace

- Properti `ResourceGroupName` telah dihapus dari jenis output `NamespaceAttributes`

## <a name="breaking-changes-to-sql-cmdlets"></a>Perubahan yang melanggar ke cmdlet Sql

Cmdlet berikut terpengaruh rilis ini:

### <a name="new-azurermsqldatabasefailovergroup"></a>New-AzureRmSqlDatabaseFailoverGroup
- Parameter `Tag` telah dihapus
- Parameter `GracePeriodWithDataLossHour` telah berganti nama menjadi `GracePeriodWithDataLossHours`

```powershell-interactive
# Old
New-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -PartnerServerName server2 -FailoverPolicy Automatic -GracePeriodWithDataLossHour 1 -Tag @{ Environment="Test" }

# New
New-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -PartnerServerName server2 -FailoverPolicy Automatic -GracePeriodWithDataLossHours 1
```

### <a name="set-azurermsqldatabasefailovergroup"></a>Set-AzureRmSqlDatabaseFailoverGroup
- Parameter `Tag` telah dihapus
- Parameter `GracePeriodWithDataLossHour` telah berganti nama menjadi `GracePeriodWithDataLossHours`

```powershell-interactive
# Old
Set-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -FailoverPolicy Automatic -GracePeriodWithDataLossHour 1 -Tag @{ Environment="Test" }

# New
Set-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -FailoverPolicy Automatic -GracePeriodWithDataLossHours 1
```

### <a name="add-azurermsqldatabasetofailovergroup"></a>Add-AzureRmSqlDatabaseToFailoverGroup
- Parameter `Tag` telah dihapus

```powershell-interactive
# Old
Add-AzureRmSqlDatabaseToFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -Database $db1 -Tag @{ Environment="Test" }

# New
Add-AzureRmSqlDatabaseToFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -Database $db1
```

###  <a name="remove-azurermsqldatabasefromfailovergroup"></a>Remove-AzureRmSqlDatabaseFromFailoverGroup
- Parameter `Tag` telah dihapus

```powershell-interactive
# Old
Remove-AzureRmSqlDatabaseFromFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -Database $db1 -Tag @{ Environment="Test" }

# New
Remove-AzureRmSqlDatabaseFromFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -Database $db1
```

### <a name="remove-azurermsqldatabasefailovergroup"></a>Remove-AzureRmSqlDatabaseFailoverGroup
- Parameter `PartnerResourceGroupName` telah dihapus
- Parameter `PartnerServerName` telah dihapus

```powershell-interactive
# Old
Remove-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -PartnerServerName server2 -PartnerResourceGroupName rg

# New
Remove-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg
```

### <a name="set-azurermsqldatabasethreatdetectionpolicy"></a>Set-AzureRmSqlDatabaseThreatDetectionPolicy
- Nilai `Usage_Anomaly` tidak lagi berlaku untuk parameter `ExcludedDetectionType`

### <a name="set-azurermsqlserverthreatdetectionpolicy"></a>Set-AzureRmSqlServerThreatDetectionPolicy
- Nilai `Usage_Anomaly` tidak lagi berlaku untuk parameter `ExcludedDetectionType`

## <a name="breaking-changes-to-storage-cmdlets"></a>Perubahan yang melanggar ke cmdlet Storage

Properti jenis output berikut terpengaruh rilis ini:

### <a name="azurestorageblobicloudblobserviceclient"></a>AzureStorageBlob.ICloudBlob.ServiceClient
- Properti berikut telah dihapus dari jenis ini (_catatan_: ini masih dapat ditemukan di properti `DefaultRequestOptions`):
    - `LocationMode`
    - `MaximumExecutionTime`
    - `ServerTimeout`
    - `ParallelOperationThreadCount`
    - `SingleBlobUploadThresholdInBytes`
- Perubahan ini memengaruhi cmdlet berikut:
    - `Get-AzureStorageBlob`
    - `Get-AzureStorageBlobContent`
    - `Get-AzureStorageBlobCopyState`
    - `Set-AzureStorageBlobContent`
    - `Start-AzureStorageBlobCopy`
    - `Stop-AzureStorageBlobCopy`

### <a name="azurestoragecontainercloudblobcontainerserviceclient"></a>AzureStorageContainer.CloudBlobContainer.ServiceClient
- Properti berikut telah dihapus dari jenis ini (_catatan_: ini masih dapat ditemukan di properti `DefaultRequestOptions`):
    - `LocationMode`
    - `MaximumExecutionTime`
    - `ServerTimeout`
    - `ParallelOperationThreadCount`
    - `SingleBlobUploadThresholdInBytes`
- Perubahan ini memengaruhi cmdlet berikut:
    - `Get-AzureStorageContainer`
    - `New-AzureStorageContainer`
    - `Set-AzureStorageContainerAcl`

### <a name="azurestoragequeuecloudqueueserviceclient"></a>AzureStorageQueue.CloudQueue.ServiceClient
- Properti berikut telah dihapus dari jenis ini (_catatan_: ini masih dapat ditemukan di properti `DefaultRequestOptions`):
    - `LocationMode`
    - `MaximumExecutionTime`
    - `RetryPolicy`
    - `ServerTimeout`
- Perubahan ini memengaruhi cmdlet berikut:
    - `Get-AzureStorageQueue`
    - `New-AzureStorageQueue`

### <a name="azurestoragetablecloudtableserviceclient"></a>AzureStorageTable.CloudTable.ServiceClient
- Properti berikut telah dihapus dari jenis ini (_catatan_: ini masih dapat ditemukan di properti `DefaultRequestOptions`):
    - `LocationMode`
    - `MaximumExecutionTime`
    - `PayloadFormat`
    - `RetryPolicy`
    - `ServerTimeout`
- Perubahan ini memengaruhi cmdlet berikut:
    - `Get-AzureStorageTable`
    - `New-AzureStorageTable`

```powershell-interactive
# Old
$LocationMode = (Get-AzureStorageBlob -Container $containername)[0].ICloudBlob.ServiceClient.LocationMode
$ParallelOperationThreadCount = (Get-AzureStorageContainer -Container $containername).CloudBlobContainer.ServiceClient.ParallelOperationThreadCount
$PayloadFormat = (Get-AzureStorageTable -Name $tablename).CloudTable.ServiceClient.PayloadFormat
$RetryPolicy = (Get-AzureStorageQueue -Name $queuename).CloudQueue.ServiceClient.RetryPolicy

# New
$LocationMode = (Get-AzureStorageBlob -Container $containername)[0].ICloudBlob.ServiceClient.DefaultRequestOptions.LocationMode
$ParallelOperationThreadCount = (Get-AzureStorageContainer -Container $containername).CloudBlobContainer.ServiceClient.DefaultRequestOptions.ParallelOperationThreadCount
$PayloadFormat = (Get-AzureStorageTable -Name $tablename).CloudTable.ServiceClient.DefaultRequestOptions.PayloadFormat
$RetryPolicy = (Get-AzureStorageQueue -Name $queuename).CloudQueue.ServiceClient.DefaultRequestOptions.RetryPolicy
```

## <a name="breaking-changes-to-profile-cmdlets"></a>Perubahan yang melanggar ke cmdlet Profile

Cmdlet dan jenis output cmdlet berikut diubah dalam rilis ini.

### <a name="add-azurermaccount-breaking-changes"></a>Perubahan yang melanggar Add-AzureRmAccount

- Parameter ```EnvironmentName``` telah dihapus dan diganti dengan ```Environment```, ```Environment``` sekarang mengambil string dan bukan objek ```AzureEnvironment```

```powershell-interactive
# Old
Add-AzureRmAccount -EnvironmentName AzureChinaCloud

# New
Add-AzureRmAccount -Environment AzureChinaCloud
```

### <a name="select-azurermprofile-was-renamed-to-import-azurermcontext"></a>Select-AzureRmProfile berganti nama menjadi Import-AzureRmContext

```Select-AzureRmProfile``` berganti nama menjadi ```Import-AzureRmContext```

```powershell-interactive
# Old
Select-AzureRmProfile -Path c:\mydir\myprofile.json

# New
Import-AzureRmContext -Path c:\mydir\myprofile.json
```

### <a name="save-azurermprofile-was-renamed-to-save-azurermcontext"></a>Save-AzureRmProfile berganti nama menjadi Save-AzureRmContext

```Save-AzureRmProfile``` berganti nama menjadi ```Save-AzureRmContext```

```powershell-interactive
# Old
Save-AzureRmProfile -Path c:\mydir\myprofile.json

# New
Save-AzureRmContext -Path c:\mydir\myprofile.json
```
### <a name="breaking-changes-to-output-psazurecontext-type"></a>Perubahan yang Melanggar ke output PSAzureContext Type

- Properti ```TokenCache``` berubah menjadi jenis yang mengimplementasikan ```IAzureTokenCache```, bukan ```byte[]```

```powershell-interactive
# Old
$bytes = (Get-AzureRmContext).TokenCache
$bytes = (Set-AzureRmContext -SubscriptionId xxx-xxx-xxx-xxx).TokenCache
$bytes = (Add-AzureRmAccount).Context.TokenCache

# New
$bytes = (Get-AzureRmContext).TokenCache.CacheData
$bytes = (Set-AzureRmContext -SubscriptionId xxx-xxx-xxx-xxx).TokenCache.CacheData
$bytes = (Add-AzureRmAccount).Context.TokenCache.CacheData
```

### <a name="breaking-changes-to-the-output-psazureaccount-type"></a>Perubahan yang Melanggar ke output PSAzureAccount Type

- Properti ```AccountType``` berubah menjadi ```Type```

```powershell-interactive
# Old
$type = (Get-AzureRmContext).Account.AccountType
$type = (Set-AzureRmContext -SubscriptionId xxx-xxx-xxx-xxx).Account.AccountType
$type = (Add-AzureRmAccount).Context.Account.AccountType

# New
$type = (Get-AzureRmContext).Account.Type
$type = (Set-AzureRmContext -SubscriptionId xxx-xxx-xxx-xxx).Account.Type
$type = (Add-AzureRmAccount).Context.Account.Type
```

### <a name="breaking-changes-to-the-output-psazuresubscription-type"></a>Perubahan yang Melanggar ke output PSAzureSubscription Type
- Properti ```SubscriptionId``` berubah menjadi ```Id```

```powershell-interactive
# Old
$id =(Get-AzureRmSubscription -SubscriptionId xxxx-xxxx-xxxx-xxxx).SubscriptionId
$id =(Add-AzureRmAccount -SubscriptionId xxxx-xxxx-xxxx-xxxx).Context.Subscription.SubscriptionId
$id =(Get-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.SubscriptionId
$id =(Set-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.SubscriptionId

# New
$id =(Get-AzureRmSubscription -SubscriptionId xxxx-xxxx-xxxx-xxxx).Id
$id =(Add-AzureRmAccount -SubscriptionId xxxx-xxxx-xxxx-xxxx).Context.Subscription.Id
$id =(Get-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.Id
$id =(Set-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.Id
```

- Properti ```SubscriptionName``` berubah menjadi ```Name```

```powershell-interactive
# Old
$name =(Get-AzureRmSubscription -SubscriptionId xxxx-xxxx-xxxx-xxxx).SubscriptionName
$name =(Add-AzureRmAccount -SubscriptionId xxxx-xxxx-xxxx-xxxx).Context.Subscription.SubscriptionName
$name =(Get-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.SubscriptionName
$name =(Set-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.SubscriptionName

# New
$name =(Get-AzureRmSubscription -SubscriptionId xxxx-xxxx-xxxx-xxxx).Name
$name =(Add-AzureRmAccount -SubscriptionId xxxx-xxxx-xxxx-xxxx).Context.Subscription.Name
$name =(Get-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.Name
$name =(Set-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Subscription.Name
```

### <a name="breaking-changes-to-the-output-psazuretenant-type"></a>Perubahan yang Melanggar ke output PSAzureAccount Type

- Properti ```TenantId``` berubah menjadi ```Id```

```powershell-interactive
# Old
$id =(Get-AzureRmTenant -TenantId xxxx-xxxx-xxxx-xxxx).TenantId
$id =(Add-AzureRmAccount -SubscriptionId xxxx-xxxx-xxxx-xxxx).Context.Tenant.TenantId
$id =(Get-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Tenant.TenantId
$id =(Set-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Tenant.TenantId

# New
$id =(Get-AzureRmTenant -TenantId xxxx-xxxx-xxxx-xxxx).Id
$id =(Add-AzureRmAccount -SubscriptionId xxxx-xxxx-xxxx-xxxx).Context.Tenant.Id
$id =(Get-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Tenant.Id
$id =(Set-AzureRmContext -SubscriptionId xxxx-xxxx-xxxx-xxxx).Tenant.Id
```

- Properti ```Domain``` berubah menjadi ```Directory```

```powershell-interactive
# Old
$tenantName =(Get-AzureRmTenant -TenantId xxxx-xxxx-xxxx-xxxx).Domain

# New
$tenantName =(Get-AzureRmTenant -TenantId xxxx-xxxx-xxxx-xxxx).Directory
```
