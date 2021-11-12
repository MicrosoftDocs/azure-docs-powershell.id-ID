---
title: Memutus perubahan untuk Microsoft Azure PowerShell 4.0.0
description: Panduan migrasi ini berisi daftar perubahan yang telah dibuat untuk Azure PowerShell rilis versi 4.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/01/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 3e5be2d8279b28e683fbe8a03b812c658fcecf33
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427988"
---
# <a name="breaking-changes-for-microsoft-azure-powershell-400"></a>Memutus perubahan untuk Microsoft Azure PowerShell 4.0.0

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Dokumen ini berfungsi sebagai pemberitahuan perubahan terbaru dan panduan migrasi bagi pelanggan Microsoft Azure PowerShell cmdlet. Setiap bagian menjelaskan impetus untuk perubahan pecah dan jalur migrasi dari resistansi paling sedikit. Untuk konteks yang lebih mendalam, silakan lihat permintaan tarik terkait dengan setiap perubahan.

## <a name="table-of-contents"></a>Daftar Isi

- [Memutus perubahan pada Cmdlet Perhitungan](#breaking-changes-to-compute-cmdlets)
- [Memutus perubahan pada cmdlet EventHub](#breaking-changes-to-eventhub-cmdlets)
- [Memutus perubahan pada Insights cmdlets](#breaking-changes-to-insights-cmdlets)
- [Memutus perubahan ke cmdlet Jaringan](#breaking-changes-to-network-cmdlets)
- [Memutus perubahan pada cmdlet ServiceBus](#breaking-changes-to-servicebus-cmdlets)
- [Memutus perubahan pada cmdlet Sql](#breaking-changes-to-sql-cmdlets)
- [Memutus perubahan pada Storage cmdlet](#breaking-changes-to-storage-cmdlets)
- [Memutus Perubahan ke Cmdlet Profil](#breaking-changes-to-profile-cmdlets)
  ## <a name="breaking-changes-to-compute-cmdlets"></a>Memutus perubahan pada Cmdlet Perhitungan

Tipe output berikut terpengaruh rilis ini:

### <a name="psvirtualmachine"></a>PSVirtualMachine
- Properti tingkat `DataDiskNames` atas dan objek `NetworkInterfaceIDs` nthe telah dihapus dari tipe `PSVirtualMachine` output. Properti ini selalu tersedia dalam properti dan objek dan akan menjadi cara yang mereka `StorageProfile` perlukan untuk diakses ke `NetworkProfile` `PSVirtualMachine` depannya.
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

## <a name="breaking-changes-to-eventhub-cmdlets"></a>Memutus perubahan pada cmdlet EventHub

Cmdlet berikut terpengaruh rilis ini:

### <a name="get-azurermeventhubnamespace"></a>Get-AzureRmEventHubNamespace
- Properti `ResourceGroupName` telah dihapus dari tipe output `NamespaceAttributes`

### <a name="new-azurermeventhubnamespace"></a>New-AzureRmEventHubNamespace
- Properti `ResourceGroupName` telah dihapus dari tipe output `NamespaceAttributes`

## <a name="breaking-changes-to-insights-cmdlets"></a>Memutus perubahan pada Insights cmdlet

Cmdlet berikut terpengaruh rilis ini:

### <a name="get-azurermusage"></a>Get-AzureRmUsage
- Cmdlet ini sudah tidak berlaku.

### <a name="remove-azurermalertrule"></a>Remove-AzureRmAlertRule
- Output cmdlet ini telah berubah dari daftar dengan objek tunggal menjadi objek tunggal; objek ini menyertakan requestId, dan kode status.

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
- Cmdlet ini sudah tidak berlaku.

### <a name="get-azurermalertrule"></a>Get-AzureRmAlertRule
- Setiap elemen output (daftar objek) dari cmdlet ini akan diratakan, misalnya, daripada mengembalikan objek dengan struktur, objek akan dikembalikan dengan struktur, yang merupakan semua atribut Dari Azure Resource plus semua atribut `{ Id, Location, Name, Tags, Properties }` `{ Id, Location, Name, Tags, Type, Description, IsEnabled, Condition, Actions, LastUpdatedTime, ...}` AlertRuleResource di tingkat atas.

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
- `AutoscaleSettingResourceName`Bidang akan ditolak karena selalu memiliki nilai yang sama seperti `Name` bidang.

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
- Output cmdlet ini akan berubah dari `Boolean` ke dan objek berisi `RequestId` dan `StatusCode`

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
- Output cmdlet ini akan berubah dari objek yang menyertakan requestId, kode status, dan sumber daya yang diperbarui atau yang baru dibuat

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
- Perintah akan diganti namanya `Update-AzureRmDiagnosticSettings`

```powershell-interactive
# Old
Set-AzureRmDiagnosticSettings

# New
Update-AzureRmDiagnosticSettings
```

## <a name="breaking-changes-to-network-cmdlets"></a>Memutus perubahan ke cmdlet Jaringan

Cmdlet berikut terpengaruh rilis ini:

### <a name="new-azurermvirtualnetworkgatewayconnection"></a>New-AzureRmVirtualNetworkGatewayConnection
- `EnableBgp` parameter telah diubah untuk mengambil `boolean` alih-alih `string`

```powershell-interactive
# Old
New-AzureRmVirtualNetworkGatewayConnection -ResourceGroupName "RG" -name "conn1" -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localnetGateway -ConnectionType IPsec -SharedKey "key" -EnableBgp "true"

# New
New-AzureRmVirtualNetworkGatewayConnection -ResourceGroupName "RG" -name "conn1" -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localnetGateway -ConnectionType IPsec -SharedKey "key" -EnableBgp $true
```

## <a name="breaking-changes-to-servicebus-cmdlets"></a>Memutus perubahan pada cmdlet ServiceBus

Cmdlet berikut terpengaruh rilis ini:

### <a name="get-azurermservicebusnamespace"></a>Get-AzureRmServiceBusNamespace
- Properti `ResourceGroupName` telah dihapus dari tipe output `NamespaceAttributes`

### <a name="new-azurermservicebusnamespace"></a>New-AzureRmServiceBusNamespace

- Properti `ResourceGroupName` telah dihapus dari tipe output `NamespaceAttributes`

## <a name="breaking-changes-to-sql-cmdlets"></a>Memutus perubahan pada cmdlet Sql

Cmdlet berikut terpengaruh rilis ini:

### <a name="new-azurermsqldatabasefailovergroup"></a>New-AzureRmSqlDatabaseFailoverGroup
- `Tag` parameter telah dihapus
- `GracePeriodWithDataLossHour` parameter telah diganti namanya menjadi `GracePeriodWithDataLossHours`

```powershell-interactive
# Old
New-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -PartnerServerName server2 -FailoverPolicy Automatic -GracePeriodWithDataLossHour 1 -Tag @{ Environment="Test" }

# New
New-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -PartnerServerName server2 -FailoverPolicy Automatic -GracePeriodWithDataLossHours 1
```

### <a name="set-azurermsqldatabasefailovergroup"></a>Set-AzureRmSqlDatabaseFailoverGroup
- `Tag` parameter telah dihapus
- `GracePeriodWithDataLossHour` parameter telah diganti namanya menjadi `GracePeriodWithDataLossHours`

```powershell-interactive
# Old
Set-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -FailoverPolicy Automatic -GracePeriodWithDataLossHour 1 -Tag @{ Environment="Test" }

# New
Set-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -FailoverPolicy Automatic -GracePeriodWithDataLossHours 1
```

### <a name="add-azurermsqldatabasetofailovergroup"></a>Add-AzureRmSqlDatabaseToFailoverGroup
- `Tag` parameter telah dihapus

```powershell-interactive
# Old
Add-AzureRmSqlDatabaseToFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -Database $db1 -Tag @{ Environment="Test" }

# New
Add-AzureRmSqlDatabaseToFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -Database $db1
```

###  <a name="remove-azurermsqldatabasefromfailovergroup"></a>Remove-AzureRmSqlDatabaseFromFailoverGroup
- `Tag` parameter telah dihapus

```powershell-interactive
# Old
Remove-AzureRmSqlDatabaseFromFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -Database $db1 -Tag @{ Environment="Test" }

# New
Remove-AzureRmSqlDatabaseFromFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -Database $db1
```

### <a name="remove-azurermsqldatabasefailovergroup"></a>Remove-AzureRmSqlDatabaseFailoverGroup
- `PartnerResourceGroupName` parameter telah dihapus
- `PartnerServerName` parameter telah dihapus

```powershell-interactive
# Old
Remove-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg -PartnerServerName server2 -PartnerResourceGroupName rg

# New
Remove-AzureRmSqlDatabaseFailoverGroup -ResourceGroupName rg -ServerName server1 -FailoverGroupName fg
```

### <a name="set-azurermsqldatabasethreatdetectionpolicy"></a>Set-AzureRmSqlDatabaseThreatDetectionPolicy
- Nilai `Usage_Anomaly` tidak lagi valid untuk parameter `ExcludedDetectionType`

### <a name="set-azurermsqlserverthreatdetectionpolicy"></a>Set-AzureRmSqlServerThreatDetectionPolicy
- Nilai `Usage_Anomaly` tidak lagi valid untuk parameter `ExcludedDetectionType`

## <a name="breaking-changes-to-storage-cmdlets"></a>Memutus perubahan pada Storage cmdlet

Properti tipe output berikut terpengaruh rilis ini:

### <a name="azurestorageblobicloudblobserviceclient"></a>AzureStorageBlob.ICloudBlob.ServiceClient
- Properti berikut ini dihapus dari tipe ini (_catatan_: properti masih dapat ditemukan `DefaultRequestOptions` dalam):
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
- Properti berikut ini dihapus dari tipe ini (_catatan_: properti masih dapat `DefaultRequestOptions` ditemukan):
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
- Properti berikut ini dihapus dari tipe ini (_catatan_: properti masih dapat `DefaultRequestOptions` ditemukan):
    - `LocationMode`
    - `MaximumExecutionTime`
    - `RetryPolicy`
    - `ServerTimeout`
- Perubahan ini memengaruhi cmdlet berikut:
    - `Get-AzureStorageQueue`
    - `New-AzureStorageQueue`

### <a name="azurestoragetablecloudtableserviceclient"></a>AzureStorageTable.CloudTable.ServiceClient
- Properti berikut ini dihapus dari tipe ini (_catatan_: properti masih dapat `DefaultRequestOptions` ditemukan):
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

## <a name="breaking-changes-to-profile-cmdlets"></a>Memutus Perubahan ke Cmdlet Profil

Cmdlet dan tipe output cmdlet berikut diubah dalam rilis ini.

### <a name="add-azurermaccount-breaking-changes"></a>Add-AzureRmAccount perubahan yang tidak terbaru

- ```EnvironmentName``` parameter telah dihapus dan diganti dengan ```Environment``` , sekarang menggunakan string dan bukan ```Environment``` ```AzureEnvironment``` objek

```powershell-interactive
# Old
Add-AzureRmAccount -EnvironmentName AzureChinaCloud

# New
Add-AzureRmAccount -Environment AzureChinaCloud
```

### <a name="select-azurermprofile-was-renamed-to-import-azurermcontext"></a>Select-AzureRmProfile diubah namanya menjadi Import-AzureRmContext

```Select-AzureRmProfile``` telah diubah namanya menjadi ```Import-AzureRmContext```

```powershell-interactive
# Old
Select-AzureRmProfile -Path c:\mydir\myprofile.json

# New
Import-AzureRmContext -Path c:\mydir\myprofile.json
```

### <a name="save-azurermprofile-was-renamed-to-save-azurermcontext"></a>Save-AzureRmProfile diubah namanya menjadi Save-AzureRmContext

```Save-AzureRmProfile``` telah diubah namanya menjadi ```Save-AzureRmContext```

```powershell-interactive
# Old
Save-AzureRmProfile -Path c:\mydir\myprofile.json

# New
Save-AzureRmContext -Path c:\mydir\myprofile.json
```
### <a name="breaking-changes-to-output-psazurecontext-type"></a>Memutus Perubahan untuk membuat output Tipe PSAzureContext

- ```TokenCache```Properti diubah menjadi tipe yang ```IAzureTokenCache``` diterapkan, bukan```byte[]```

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

### <a name="breaking-changes-to-the-output-psazureaccount-type"></a>Memutus Perubahan ke output Tipe PSAzureAccount

- ```AccountType```Properti telah diubah menjadi```Type```

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

### <a name="breaking-changes-to-the-output-psazuresubscription-type"></a>Memutus Perubahan ke Tipe PSAzureSubscription output
- ```SubscriptionId```Properti telah diubah menjadi```Id```

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

- ```SubscriptionName```Properti telah diubah menjadi```Name```

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

### <a name="breaking-changes-to-the-output-psazuretenant-type"></a>Memutus Perubahan pada Output Tipe PSAzureTenant

- ```TenantId```Properti telah diubah menjadi```Id```

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

- ```Domain```Properti telah diubah menjadi```Directory```

```powershell-interactive
# Old
$tenantName =(Get-AzureRmTenant -TenantId xxxx-xxxx-xxxx-xxxx).Domain

# New
$tenantName =(Get-AzureRmTenant -TenantId xxxx-xxxx-xxxx-xxxx).Directory
```
