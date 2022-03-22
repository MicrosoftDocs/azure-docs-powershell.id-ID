---
title: Perubahan breaking untuk Microsoft Azure PowerShell 5.0.0
description: Panduan migrasi ini berisi daftar perubahan melanggar yang dibuat untuk Azure PowerShell dalam rilis versi 5.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/01/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 81f52ee8b84f60d59a7f2d53b6675129ac054fd6
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425050"
---
# <a name="breaking-changes-for-microsoft-azure-powershell-500"></a>Perubahan breaking untuk Microsoft Azure PowerShell 5.0.0

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Dokumen ini berfungsi sebagai pemberitahuan perubahan dan panduan migrasi bagi konsumen cmdlet Microsoft Azure PowerShell. Setiap bagian menggambarkan dorongan untuk perubahan yang melanggar dan jalur migrasi resistensi paling sedikit. Untuk konteks mendalam, silakan lihat permintaan pull yang terkait dengan setiap perubahan.

## <a name="table-of-contents"></a>Daftar Isi

- [Perubahan yang melanggar ke cmdlet ApiManagement](#breaking-changes-to-apimanagement-cmdlets)
- [Perubahan yang melanggar ke cmdlet Batch](#breaking-changes-to-batch-cmdlets)
- [Perubahan yang melanggar ke cmdlet Compute](#breaking-changes-to-compute-cmdlets)
- [Perubahan yang melanggar ke cmdlet EventHub](#breaking-changes-to-eventhub-cmdlets)
- [Perubahan yang melanggar ke cmdlet Insights](#breaking-changes-to-insights-cmdlets)
- [Perubahan yang melanggar ke cmdlet Network](#breaking-changes-to-network-cmdlets)
- [Perubahan yang melanggar ke cmdlet Resources](#breaking-changes-to-resources-cmdlets)
- [Perubahan yang melanggar ke Cmdlet ServiceBus](#breaking-changes-to-servicebus-cmdlets)

## <a name="breaking-changes-to-apimanagement-cmdlets"></a>Melanggar perubahan pada cmdlet ApiManagement

### <a name="new-azurermapimanagementbackendproxy"></a>**New-AzureRmApiManagementBackendProxy**
- Parameter "UserName" dan "Password" sedang diganti untuk mendukung PSCredential

```powershell-interactive
# Old
New-AzureRmApiManagementBackendProxy [other required parameters] -UserName "plain-text string" -Password "plain-text string"

# New
New-AzureRmApiManagementBackendProxy [other required parameters] -Credential $PSCredentialVariable
```

### <a name="new-azurermapimanagementuser"></a>**New-AzureRmApiManagementUser**
- Parameter "Kata Sandi" diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmApiManagementUser [other required parameters] -Password "plain-text string"

# New
New-AzureRmApiManagementUser [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermapimanagementuser"></a>**Set-AzureRmApiManagementUser**
- Parameter "Kata Sandi" diganti untuk mendukung SecureString

```powershell-interactive
# Old
Set-AzureRmApiManagementUser [other required parameters] -Password "plain-text string"

# New
Set-AzureRmApiManagementUser [other required parameters] -Password $SecureStringVariable
```

## <a name="breaking-changes-to-batch-cmdlets"></a>Perubahan yang melanggar ke cmdlet Batch

### <a name="new-azurebatchcertificate"></a>**New-AzureBatchCertificate**
- Parameter `Password` diganti untuk mendukung string Aman

```powershell-interactive
# Old
New-AzureBatchCertificate [other required parameters] -Password "plain-text string"

# New
New-AzureBatchCertificate [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurebatchcomputenodeuser"></a>**New-AzureBatchComputeNodeUser**
- Parameter `Password` diganti untuk mendukung string Aman

```powershell-interactive
# Old
New-AzureBatchComputeNodeUser [other required parameters] -Password "plain-text string"

# New
New-AzureBatchComputeNodeUser [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermbatchcomputenodeuser"></a>**Set-AzureRmBatchComputeNodeUser**
- Parameter `Password` diganti untuk mendukung string Aman

```powershell-interactive
# Old
Set-AzureRmBatchComputeNodeUser [other required parameters] -Password "plain-text string"

# New
Set-AzureRmBatchComputeNodeUser [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurebatchtask"></a>**New-AzureBatchTask**
 - Melepas pengalih `RunElevated` dan menggantinya dengan `UserIdentity`.

```powershell-interactive
# Old
New-AzureBatchTask -Id $taskId1 -JobId $jobId -CommandLine "cmd /c echo hello" -RunElevated $TRUE

# New
$autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
$userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
New-AzureBatchTask -Id $taskId1 -JobId $jobId -CommandLine "cmd /c echo hello" -UserIdentity $userIdentity
```

Hal ini juga berdampak pada properti `RunElevated` pada `PSCloudTask`, `PSStartTask`, `PSJobManagerTask`, `PSJobPreparationTask`, dan `PSJobReleaseTask`.

### <a name="psmultiinstancesettings"></a>**PSMultiInstanceSettings**

- Konstruktor `PSMultiInstanceSettings` tidak lagi mengambil parameter `numberOfInstances` yang diperlukan, melainkan membutuhkan parameter `coordinationCommandLine` yang diperlukan.

```powershell-interactive
# Old
$settings = New-Object Microsoft.Azure.Commands.Batch.Models.PSMultiInstanceSettings -ArgumentList @(2)
$settings.CoordinationCommandLine = "cmd /c echo hello"
New-AzureBatchTask [other parameters] -MultiInstanceSettings $settings

# New
$settings = New-Object Microsoft.Azure.Commands.Batch.Models.PSMultiInstanceSettings -ArgumentList @("cmd /c echo hello", 2)
New-AzureBatchTask [other parameters] -MultiInstanceSettings $settings
```

### <a name="get-azurebatchtask"></a>**Get-AzureBatchTask**
 - Menghapus properti `RunElevated` pada `PSCloudTask`. Properti `UserIdentity` telah ditambahkan untuk menggantikan `RunElevated`.

```powershell-interactive
# Old
$task = Get-AzureBatchTask [parameters]
$task.RunElevated

# New
$task = Get-AzureBatchTask [parameters]
$task.UserIdentity.AutoUser.ElevationLevel
```

Hal ini juga berdampak pada properti `RunElevated` pada `PSCloudTask`, `PSStartTask`, `PSJobManagerTask`, `PSJobPreparationTask`, dan `PSJobReleaseTask`.

### <a name="multiple-types"></a>**Beberapa tipe**

- Mengganti nama properti `SchedulingError` di `PSExitConditions` menjadi `PreProcessingError`.

```powershell-interactive
# Old
$task = Get-AzureBatchTask [parameters]
$task.ExitConditions.SchedulingError

# New
$task = Get-AzureBatchTask [parameters]
$task.ExitConditions.PreProcessingError
```

### <a name="multiple-types"></a>**Beberapa tipe**

- Mengganti nama properti `SchedulingError` pada `PSJobPreparationTaskExecutionInformation`, `PSJobReleaseTaskExecutionInformation`, `PSStartTaskInformation`, `PSSubtaskInformation`, dan `PSTaskExecutionInformation` ke `FailureInformation`.
  - `FailureInformation` dikembalikan setiap kali ada kegagalan tugas. Ini termasuk semua kasus kesalahan penjadwalan sebelumnya, serta kode keluar tugas yang tidak nol, dan kegagalan unggah file dari fitur file keluaran baru.
  - Ini disusun sama seperti sebelumnya, jadi tidak diperlukan perubahan kode saat menggunakan jenis ini.

```powershell-interactive
# Old
$task = Get-AzureBatchTask [parameters]
$task.ExecutionInformation.SchedulingError

# New
$task = Get-AzureBatchTask [parameters]
$task.ExecutionInformation.FailureInformation
```

Ini juga berdampak: Get-AzureBatchPool, Get-AzureBatchSubtask, dan Get-AzureBatchJobPreparationAndReleaseTaskStatus

### <a name="new-azurebatchpool"></a>**New-AzureBatchPool**
 - `TargetDedicated` dihapus dan diganti dengan `TargetDedicatedComputeNodes` dan `TargetLowPriorityComputeNodes`.
 - `TargetDedicatedComputeNodes` memiliki alias `TargetDedicated`.

```powershell-interactive
# Old
New-AzureBatchPool [other parameters] [-TargetDedicated <Int32>]

# New
New-AzureBatchPool [other parameters] [-TargetDedicatedComputeNodes <Int32>] [-TargetLowPriorityComputeNodes <Int32>]
```

Ini juga berdampak: Start-AzureBatchPoolResize

### <a name="get-azurebatchpool"></a>**Get-AzureBatchPool**
 - Mengganti nama properti `TargetDedicated` dan `CurrentDedicated` pada `PSCloudPool`ke `TargetDedicatedComputeNodes` dan `CurrentDedicatedComputeNodes`.

```powershell-interactive
# Old
$pool = Get-AzureBatchPool [parameters]
$pool.TargetDedicated
$pool.CurrentDedicated

# New
$pool = Get-AzureBatchPool [parameters]
$pool.TargetDedicatedComputeNodes
$pool.CurrentDedicatedComputeNodes
```

### <a name="type-pscloudpool"></a>**Ketik PSCloudPool**

- Mengganti nama `ResizeError` menjadi `ResizeErrors` pada `PSCloudPool`, dan sekarang menjadi koleksi.

```powershell-interactive
# Old
$pool = Get-AzureBatchPool [parameters]
$pool.ResizeError

# New
$pool = Get-AzureBatchPool [parameters]
$pool.ResizeErrors[0]
```

### <a name="new-azurebatchjob"></a>**New-AzureBatchJob**
- Mengganti nama properti `TargetDedicated` pada `PSPoolSpecification` menjadi `TargetDedicatedComputeNodes`.

```powershell-interactive
# Old
$poolInfo = New-Object Microsoft.Azure.Commands.Batch.Models.PSPoolInformation
$poolInfo.AutoPoolSpecification = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoPoolSpecification
$poolInfo.AutoPoolSpecification.PoolSpecification = New-Object Microsoft.Azure.Commands.Batch.Models.PSPoolSpecification
$poolInfo.AutoPoolSpecification.PoolSpecification.TargetDedicated = 5
New-AzureBatchJob [other parameters] -PoolInformation $poolInfo

# New
$poolInfo = New-Object Microsoft.Azure.Commands.Batch.Models.PSPoolInformation
$poolInfo.AutoPoolSpecification = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoPoolSpecification
$poolInfo.AutoPoolSpecification.PoolSpecification = New-Object Microsoft.Azure.Commands.Batch.Models.PSPoolSpecification
$poolInfo.AutoPoolSpecification.PoolSpecification.TargetDedicatedComputeNodes = 5
New-AzureBatchJob [other parameters] -PoolInformation $poolInfo
```

### <a name="get-azurebatchnodefile"></a>**Get-AzureBatchNodeFile**
 - `Name` dihapus dan diganti dengan `Path`.
 - `Path` memiliki alias `Name`.

```powershell-interactive
# Old
Get-AzureBatchNodeFile [other parameters] [[-Name] <String>]

# New
Get-AzureBatchNodeFile [other parameters] [[-Path] <String>]
```

Ini juga berdampak: Get-AzureBatchNodeFileContent, Remove-AzureBatchNodeFile

### <a name="type-psnodefile"></a>Ketik **PSNodeFile**

 - Mengganti nama properti `Name` pada `PSNodeFile` menjadi `Path`.

```powershell-interactive
# Old
$file = Get-AzureBatchNodeFile [parameters]
$file.Name

# New
$file = Get-AzureBatchNodeFile [parameters]
$file.Path
```

### <a name="get-azurebatchsubtask"></a>**Get-AzureBatchSubtask**
- Properti `PreviousState` dan `State` dari `PSSubtaskInformation` tidak lagi merupakan jenis `TaskState`, melainkan dari jenis `SubtaskState`.
  - Tidak seperti `TaskState`, `SubtaskState` tidak memiliki nilai `Active`, karena tidak mungkin bagi subtugas berada dalam status `Active`.

```powershell-interactive
# Old
$subtask = Get-AzureBatchSubtask [parameters]
if ($subtask.State -eq Microsoft.Azure.Batch.Common.TaskState.Running) { }

# New
$subtask = Get-AzureBatchSubtask [parameters]
if ($subtask.State -eq Microsoft.Azure.Batch.Common.SubtaskState.Running) { }
```

## <a name="breaking-changes-to-compute-cmdlets"></a>Perubahan yang melanggar ke cmdlet Compute

### <a name="set-azurermvmaccessextension"></a>**Set-AzureRmVMAccessExtension**
- Parameter "UserName" dan "Password" sedang diganti untuk mendukung PSCredential

```powershell-interactive
# Old
Set-AzureRmVMAccessExtension [other required parameters] -UserName "plain-text string" -Password "plain-text string"

# New
Set-AzureRmVMAccessExtension [other required parameters] -Credential $PSCredential
```

## <a name="breaking-changes-to-eventhub-cmdlets"></a>Perubahan yang melanggar ke cmdlet EventHub

### <a name="new-azurermeventhubnamespaceauthorizationrule"></a>**New-AzureRmEventHubNamespaceAuthorizationRule**
- Cmdlet 'New-AzureRmEventHubNamespaceAuthorizationRule' telah dihapus. Gunakan cmdlet 'New-AzureRmEventHubAuthorizationRule'

### <a name="get-azurermeventhubnamespaceauthorizationrule"></a>**Get-AzureRmEventHubNamespaceAuthorizationRule**
- Cmdlet 'Get-AzureRmEventHubNameSpaceAuthorizationRule' telah dihapus. Gunakan cmdlet 'Get-AzureRmEventHubAuthorizationRule'

### <a name="set-azurermeventhubnamespaceauthorizationrule"></a>**Set-AzureRmEventHubNamespaceAuthorizationRule**
- Cmdlet 'Set-AzureRmEventHubNamespaceAuthorizationRule' telah dihapus. Gunakan cmdlet 'Set-AzureRmEventHubAuthorizationRule'

### <a name="remove-azurermeventhubnamespaceauthorizationrule"></a>**Remove-AzureRmEventHubNamespaceAuthorizationRule**
- Cmdlet 'Remove-AzureRmEventHubNamespaceAuthorizationRule' telah dihapus. Gunakan cmdlet 'Remove-AzureRmEventHubAuthorizationRule'

### <a name="new-azurermeventhubnamespacekey"></a>**New-AzureRmEventHubNamespaceKey**
- Cmdlet 'New-AzureRmEventHubNamespaceKey' telah dihapus. Gunakan cmdlet 'New-AzureRmEventHubKey'

### <a name="get-azurermeventhubnamespacekey"></a>**Get-AzureRmEventHubNamespaceKey**
- Cmdlet 'Get-AzureRmEventHubNamespaceKey' telah dihapus. Gunakan cmdlet 'Get-AzureRmEventHubKey'

### <a name="new-azurermeventhubnamespace"></a>**New-AzureRmEventHubNamespace**
- Properti 'Status' dan 'Enabled' dari NamespceAttributes akan dihapus.

```powershell-interactive
# Old
# The $namespace has Status and Enabled property
$namespace = New-AzureRmEventHubNamespace <parameters>
$namespace.Status
$namespace.Enabled

# New
# The call remains the same, but the returned values NameSpace object will not have the Status and Enabled property
$namespace = Get-AzureRmEventHubNamespace <parameters>
```

### <a name="get-azurermeventhubnamespace"></a>**Get-AzureRmEventHubNamespace**
- Properti 'Status' dan 'Enabled' dari NamespceAttributes akan dihapus.

```powershell-interactive
# Old
# The $namespace has Status and Enabled property
$namespace = Get-AzureRmEventHubNamespace <parameters>
$namespace.Status
$namespace.Enabled

# New
# The call remains the same, but the returned values NameSpace object will not have the Status and Enabled property
$namespace = Get-AzureRmEventHubNamespace <parameters>
```

### <a name="set-azurermeventhubnamespace"></a>**Set-AzureRmEventHubNamespace**
- Properti 'Status' dan 'Enabled' dari NamespceAttributes akan dihapus.

```powershell-interactive
# Old
# The $namespace has Status and Enabled property
$namespace = Set-AzureRmEventHubNamespace <parameters>
$namespace.Status
$namespace.Enabled

# New
# The call remains the same, but the returned values NameSpace object will not have the Status and Enabled property
$namespace = Set-AzureRmEventHubNamespace <parameters>
```

### <a name="new-azurermeventhubconsumergroup"></a>**New-AzureRmEventHubConsumerGroup**
- Properti 'EventHubPath' dari ConsumerGroupAttributes akan dihapus.

```powershell-interactive
# Old
# The $consumergroup has EventHubPath property
$consumergroup = New-AzureRmEventHubConsumerGroup <parameters>
$consumergroup.EventHubPath

# New
# The call remains the same, but the returned values ConsumerGroup object will not have the EventHubPath property
$consumergroup = New-AzureRmEventHubConsumerGroup <parameters>
```

### <a name="set-azurermeventhubconsumergroup"></a>**Set-AzureRmEventHubConsumerGroup**
- Properti 'EventHubPath' dari ConsumerGroupAttributes akan dihapus.

```powershell-interactive
# Old
# The $consumergroup has EventHubPath property
$consumergroup = Set-AzureRmEventHubConsumerGroup <parameters>
$consumergroup.EventHubPath

# New
# The call remains the same, but the returned values ConsumerGroup object will not have the EventHubPath property
$consumergroup = Set-AzureRmEventHubConsumerGroup <parameters>
```

### <a name="get-azurermeventhubconsumergroup"></a>**Get-AzureRmEventHubConsumerGroup**
- Properti 'EventHubPath' dari ConsumerGroupAttributes akan dihapus.

```powershell-interactive
# Old
# The $consumergroup has EventHubPath property
$consumergroup = Get-AzureRmEventHubConsumerGroup <parameters>
$consumergroup.EventHubPath

# New
# The call remains the same, but the returned values ConsumerGroup object will not have the EventHubPath property
$consumergroup = Get-AzureRmEventHubConsumerGroup <parameters>
```

## <a name="breaking-changes-to-insights-cmdlets"></a>Perubahan yang melanggar ke cmdlet Insights

### <a name="add-azurermlogalertrule"></a>**Add-AzureRMLogAlertRule**
- Cmdlet **Add-AzureRMLogAlertRule** telah tidak digunakan lagi
- Setelah 1 Oktober menggunakan cmdlet ini tidak akan lagi berpengaruh karena fungsi ini sedang dialihkan ke Peringatan Log Aktivitas. Lihat https://aka.ms/migratemealerts untuk mengetahui informasi selengkapnya.

### <a name="get-azurermusage"></a>**Get-AzureRMUsage**
- Cmdlet **Get-AzureRMUsage** telah tidak digunakan lagi

### <a name="get-azurermalerthistory--get-azurermautoscalehistory--get-azurermlogs"></a>**Get-AzureRmAlertHistory** / **Get-AzureRmAutoscaleHistory** / **Get-AzureRmLogs**
- Perubahan output: Bidang EventChannels dari objek EventData (dikembalikan oleh cmdlet ini) sedang tidak digunakan lagi karena sekarang mengembalikan nilai konstan (Admin,Operation.)

### <a name="get-azurermalertrule"></a>**Get-AzureRmAlertRule**
- Perubahan output: Output cmdlet ini akan diratakan, yaitu penghapusan bidang properti, untuk meningkatkan pengalaman pengguna.

```powershell-interactive
# Old
$rules = Get-AzureRmAlertRule -ResourceGroup $resourceGroup
if ($rules -and $rules.count -ge 1)
{
    Write-Host -Foreground Red "Error updating alert rule"
    Write-Host $rules[0].Id
    Write-Host $rules[0].Properties.IsEnabled
    Write-Host $rules[0].Properties.Condition
}

# New
$rules = Get-AzureRmAlertRule -ResourceGroup $resourceGroup
if ($rules -and $rules.count -ge 1)
{
    Write-Host -Foreground red "Error updating alert rule"
    Write-Host $rules[0].Id

    # Properties will remain for a while
    Write-Host $rules[0].Properties.IsEnabled

    # But the properties will be at the top level too. Later Properties will be removed
    Write-Host $rules[0].IsEnabled
    Write-Host $rules[0].Condition
}
```

### <a name="get-azurermautoscalesetting"></a>**Get-AzureRmAutoscaleSetting**
- Perubahan output: Bidang AutoscaleSettingResourceName akan tidak digunakan lagi karena selalu sama dengan bidang Nama.

```powershell-interactive
# Old
$s1 = Get-AzureRmAutoscaleSetting -ResourceGroup $resourceGroup -Name MySetting
if ($s1.AutoscaleSettingResourceName -ne $s1.Name)
{
    Write-Host "There is something wrong with the name"
}

# New
$s1 = Get-AzureRmAutoscaleSetting -ResourceGroup $resourceGroup -Name MySetting

# there won't be a AutoscaleSettingResourceName
Write-Host $s1.Name
```

### <a name="remove-azurermalertrule--remove-azurermlogprofile"></a>**Remove-AzureRmAlertRule** / **Remove-AzureRmLogProfile**
- Perubahan output: Jenis output akan berubah untuk mengembalikan satu objek yang berisi id permintaan dan kode status.

```powershell-interactive
# Old
$s1 = Remove-AzureRmAlertRule -ResourceGroup $resourceGroup -name $ruleName
if ($s1 -ne $null)
{
    $r = $s1[0].RequestId
    $s = $s1[0].StatusCode
}

# New
$s1 = Remove-AzureRmAlertRule -ResourceGroup $resourceGroup -name $ruleName
$r = $s1.RequestId
$s = $s1.StatusCode
```

## <a name="breaking-changes-to-network-cmdlets"></a>Melanggar perubahan pada cmdlet Network

### <a name="add-azurermapplicationgatewaysslcertificate"></a>**Add-AzureRmApplicationGatewaySslCertificate**
- Parameter "Kata Sandi" diganti untuk mendukung SecureString

```powershell-interactive
# Old
Add-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password "plain-text string"

# New
Add-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermapplicationgatewaysslcertificate"></a>**New-AzureRmApplicationGatewaySslCertificate**
- Parameter "Kata Sandi" diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password "plain-text string"

# New
New-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermapplicationgatewaysslcertificate"></a>**Set-AzureRmApplicationGatewaySslCertificate**
- Parameter "Kata Sandi" diganti untuk mendukung SecureString

```powershell-interactive
# Old
Set-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password "plain-text string"

# New
Set-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password $SecureStringVariable
```

## <a name="breaking-changes-to-resources-cmdlets"></a>Perubahan yang melanggar ke cmdlet Resources

### <a name="new-azurermadappcredential"></a>**New-AzureRmADAppCredential**
- Parameter "Kata Sandi" diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmADAppCredential [other required parameters] -Password "plain-text string"

# New
New-AzureRmADAppCredential [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermadapplication"></a>**New-AzureRmADApplication**
- Parameter "Kata Sandi" diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmADApplication [other required parameters] -Password "plain-text string"

# New
New-AzureRmADApplication [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermadserviceprincipal"></a>**New-AzureRmADServicePrincipal**
- Parameter "Kata Sandi" diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmADServicePrincipal [other required parameters] -Password "plain-text string"

# New
New-AzureRmADServicePrincipal [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermadspcredential"></a>**New-AzureRmADSpCredential**
- Parameter "Kata Sandi" diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmADSpCredential [other required parameters] -Password "plain-text string"

# New
New-AzureRmADSpCredential [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermaduser"></a>**New-AzureRmADUser**
- Parameter "Kata Sandi" diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmADUser [other required parameters] -Password "plain-text string"

# New
New-AzureRmADUser [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermaduser"></a>**Set-AzureRmADUser**
- Parameter "Kata Sandi" diganti untuk mendukung SecureString

```powershell-interactive
# Old
Set-AzureRmADUser [other required parameters] -Password "plain-text string"

# New
Set-AzureRmADUser [other required parameters] -Password $SecureStringVariable
```

## <a name="breaking-changes-to-servicebus-cmdlets"></a>Perubahan yang melanggar ke cmdlet ServiceBus

### <a name="get-azurermservicebustopicauthorizationrule"></a>**Get-AzureRmServiceBusTopicAuthorizationRule**
- Cmdlet 'Get-AzureRmServiceBusTopicAuthorizationRule' telah dihapus. Gunakan cmdlet 'Get-AzureRmServiceBusAuthorizationRule'.

### <a name="get-azurermservicebustopickey"></a>**Get-AzureRmServiceBusTopicKey**
- Cmdlet 'Get-AzureRmServiceBusTopicKey' telah dihapus. Gunakan cmdlet 'Get-AzureRmServiceBusKey'.

### <a name="new-azurermservicebustopicauthorizationrule"></a>**New-AzureRmServiceBusTopicAuthorizationRule**
- Cmdlet 'New-AzureRmServiceBusTopicAuthorizationRule' telah dihapus. Gunakan cmdlet 'New-AzureRmServiceBusAuthorizationRule'.

### <a name="new-azurermservicebustopickey"></a>**New-AzureRmServiceBusTopicKey**
- Cmdlet 'New-AzureRmServiceBusTopicKey' telah dihapus. Gunakan cmdlet 'New-AzureRmServiceBusKey'.

### <a name="remove-azurermservicebustopicauthorizationrule"></a>**Remove-AzureRmServiceBusTopicAuthorizationRule**
- Cmdlet 'Remove-AzureRmServiceBusTopicAuthorizationRule' telah dihapus. Gunakan cmdlet 'Remove-AzureRmServiceBusAuthorizationRule'.

### <a name="set-azurermservicebustopicauthorizationrule"></a>**Set-AzureRmServiceBusTopicAuthorizationRule**
- Cmdlet 'Set-AzureRmServiceBusTopicAuthorizationRule' telah dihapus. Gunakan cmdlet 'Set-AzureRmServiceBusAuthorizationRule'.

### <a name="new-azurermservicebusnamespacekey"></a>**New-AzureRmServiceBusNamespaceKey**
- Cmdlet 'New-AzureRmServiceBusNamespaceKey' telah dihapus. Gunakan cmdlet 'New-AzureRmServiceBusKey'.

### <a name="get-azurermservicebusqueueauthorizationrule"></a>**Get-AzureRmServiceBusQueueAuthorizationRule**
- Cmdlet 'Get-AzureRmServiceBusQueueAuthorizationRule' telah dihapus. Gunakan cmdlet 'Get-AzureRmServiceBusAuthorizationRule'.

### <a name="get-azurermservicebusqueuekey"></a>**Get-AzureRmServiceBusQueueKey**
- Cmdlet 'Get-AzureRmServiceBusQueueKey' telah dihapus. Gunakan cmdlet 'Get-AzureRmServiceBusKey'.

### <a name="new-azurermservicebusqueueauthorizationrule"></a>**New-AzureRmServiceBusQueueAuthorizationRule**
- Cmdlet 'New-AzureRmServiceBusQueueAuthorizationRule' telah dihapus. Gunakan cmdlet 'New-AzureRmServiceBusAuthorizationRule'.

### <a name="new-azurermservicebusqueuekey"></a>**New-AzureRmServiceBusQueueKey**
- Cmdlet 'New-AzureRmServiceBusQueueKey' telah dihapus. Gunakan cmdlet 'New-AzureRmServiceBusKey'.

### <a name="remove-azurermservicebusqueueauthorizationrule"></a>**Remove-AzureRmServiceBusQueueAuthorizationRule**
- Cmdlet 'Remove-AzureRmServiceBusQueueAuthorizationRule' telah dihapus. Gunakan cmdlet 'GRemove-AzureRmServiceBusAuthorizationRule'.

### <a name="set-azurermservicebusqueueauthorizationrule"></a>**Set-AzureRmServiceBusQueueAuthorizationRule**
- Cmdlet 'Set-AzureRmServiceBusQueueAuthorizationRule' telah dihapus. Gunakan cmdlet 'Set-AzureRmServiceBusAuthorizationRule'.

### <a name="get-azurermservicebusnamespaceauthorizationrule"></a>**Get-AzureRmServiceBusNamespaceAuthorizationRule**
- Cmdlet 'Get-AzureRmServiceBusNameNamespaceAuthorizationRule' telah dihapus. Gunakan cmdlet 'Get-AzureRmServiceBusAuthorizationRule'.

### <a name="get-azurermservicebusnamespacekey"></a>**Get-AzureRmServiceBusNamespaceKey**
- Cmdlet 'Get-AzureRmServiceBusNamespaceKey' telah dihapus. Gunakan cmdlet 'Get-AzureRmServiceBusKey'.

### <a name="new-azurermservicebusnamespaceauthorizationrule"></a>**New-AzureRmServiceBusNamespaceAuthorizationRule**
- Cmdlet 'New-AzureRmServiceBusNameNamespaceAuthorizationRule' telah dihapus. Gunakan cmdlet 'New-AzureRmServiceBusAuthorizationRule'.

### <a name="remove-azurermservicebusnamespaceauthorizationrule"></a>**Remove-AzureRmServiceBusNamespaceAuthorizationRule**
- Cmdlet 'Remove-AzureRmServiceBusNameSpaceAuthorizationRule' telah dihapus. Gunakan cmdlet 'Remove-AzureRmServiceBusAuthorizationRule'.

### <a name="set-azurermservicebusnamespaceauthorizationrule"></a>**Set-AzureRmServiceBusNamespaceAuthorizationRule**
- Cmdlet 'Set-AzureRmServiceBusNameNamespaceAuthorizationRule' telah dihapus. Gunakan cmdlet 'Set-AzureRmServiceBusAuthorizationRule'.

### <a name="type-namespaceattributes"></a>**Ketik NamespaceAttributes**
- Properti berikut telah dihapus
    - Aktif
    - Status

```powershell-interactive
# Old
# The $namespace has Status and Enabled property
$namespace = Get-AzureRmServiceBusNamespace <parameters>
$namespace.Status
$namespace.Enabled

# New
# The call remains the same, but the returned values NameSpace object will not have the Enabled and Status properties
$namespace = Get-AzureRmServiceBusNamespace <parameters>
```

### <a name="type-queueattribute"></a>**Ketik QueueAttribute**
- Properti berikut ditandai sebagai usang:
    - EnableBatchedOperations
    - EntityAvailabilityStatus
    - IsAnonymousAccessible
    - SupportOrdering

```powershell-interactive
# Old
# The $queue has EntityAvailabilityStatus, EnableBatchedOperations, IsAnonymousAccessible and SupportOrdering properties
$queue = Get-AzureRmServiceBusQueue <parameters>
$queue.EntityAvailabilityStatus
$queue.EnableBatchedOperations
$queue.IsAnonymousAccessible
$queue.SupportOrdering

# New
# The call remains the same, but the returned values Queue object will not have the EntityAvailabilityStatus, EnableBatchedOperations, IsAnonymousAccessible and SupportOrdering properties
$queue = Get-AzureRmServiceBusQueue <parameters>
```

### <a name="type-topicattribute"></a>**Ketik TopicAttribute**
- Properti berikut ditandai sebagai usang:
    - Lokasi
    - IsExpress
    - IsAnonymousAccessible
    - FilteringMessagesBeforePublishing
    - EnableSubscriptionPartitioning
    - EntityAvailabilityStatus

```powershell-interactive
# Old
# The $topic has EntityAvailabilityStatus, EnableSubscriptionPartitioning, IsAnonymousAccessible, IsExpress, Location and FilteringMessagesBeforePublishing properties
$topic = Get-AzureRmServiceBusTopic <parameters>
$topic.EntityAvailabilityStatus
$topic.EnableSubscriptionPartitioning
$topic.IsAnonymousAccessible
$topic.IsExpress
$topic.FilteringMessagesBeforePublishing
$topic.Location

# New
# The call remains the same, but the returned values Topic object will not have the EntityAvailabilityStatus, EnableBatchedOperations, IsAnonymousAccessible and SupportOrdering properties
$topic = Get-AzureRmServiceBusTopic <parameters>
```

### <a name="type-subscriptionattribute"></a>**Ketik SubscriptionAttribute**
- Properti berikut ditandai sebagai usang
    - DeadLetteringOnFilterEvaluationExceptions
    - EntityAvailabilityStatus
    - IsReadOnly
    - Lokasi

```powershell-interactive
# Old
# The $subscription has EntityAvailabilityStatus, EnableSubscriptionPartitioning, IsAnonymousAccessible, IsExpress, Location and FilteringMessagesBeforePublishing properties
$subscription = Get-AzureRmServiceBussubscription <parameters>
$subscription.EntityAvailabilityStatus
$subscription.EnableSubscriptionPartitioning
$subscription.IsAnonymousAccessible
$subscription.IsExpress
$subscription.FilteringMessagesBeforePublishing
$subscription.Location

# New
# The call remains the same, but the returned values Topic object will not have the EntityAvailabilityStatus, EnableBatchedOperations, IsAnonymousAccessible and SupportOrdering properties
$subscription = Get-AzureRmServiceBussubscription <parameters>
```
