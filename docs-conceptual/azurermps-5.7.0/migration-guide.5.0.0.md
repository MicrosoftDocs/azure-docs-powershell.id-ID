---
title: Memutus perubahan untuk Microsoft Azure PowerShell 5.0.0
description: Panduan migrasi ini berisi daftar perubahan yang telah dibuat untuk Azure PowerShell di rilis versi 5.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/01/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 81f52ee8b84f60d59a7f2d53b6675129ac054fd6
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425050"
---
# <a name="breaking-changes-for-microsoft-azure-powershell-500"></a>Memutus perubahan untuk Microsoft Azure PowerShell 5.0.0

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Dokumen ini berfungsi sebagai pemberitahuan perubahan terbaru dan panduan migrasi bagi pelanggan Microsoft Azure PowerShell cmdlet. Setiap bagian menjelaskan impetus untuk perubahan pecah dan jalur migrasi dari resistansi paling sedikit. Untuk konteks yang lebih mendalam, silakan lihat permintaan tarik terkait dengan setiap perubahan.

## <a name="table-of-contents"></a>Daftar Isi

- [Memutus perubahan pada cmdlet ApiManagement](#breaking-changes-to-apimanagement-cmdlets)
- [Memutus perubahan ke cmdlet Kumpulan](#breaking-changes-to-batch-cmdlets)
- [Memutus perubahan pada Cmdlet Perhitungan](#breaking-changes-to-compute-cmdlets)
- [Memutus perubahan pada cmdlet EventHub](#breaking-changes-to-eventhub-cmdlets)
- [Memutus perubahan pada Insights cmdlet](#breaking-changes-to-insights-cmdlets)
- [Memutus perubahan ke cmdlet Jaringan](#breaking-changes-to-network-cmdlets)
- [Memutus perubahan ke cmdlet Sumber Daya](#breaking-changes-to-resources-cmdlets)
- [Memutus Perubahan pada Cmdlet ServiceBus](#breaking-changes-to-servicebus-cmdlets)

## <a name="breaking-changes-to-apimanagement-cmdlets"></a>Memutus perubahan pada cmdlet ApiManagement

### <a name="new-azurermapimanagementbackendproxy"></a>**New-AzureRmApiManagementBackendProxy**
- Parameter "UserName" dan "Password" akan diganti untuk mendukung PSCredential

```powershell-interactive
# Old
New-AzureRmApiManagementBackendProxy [other required parameters] -UserName "plain-text string" -Password "plain-text string"

# New
New-AzureRmApiManagementBackendProxy [other required parameters] -Credential $PSCredentialVariable
```

### <a name="new-azurermapimanagementuser"></a>**New-AzureRmApiManagementUser**
- Parameter "Password" akan diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmApiManagementUser [other required parameters] -Password "plain-text string"

# New
New-AzureRmApiManagementUser [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermapimanagementuser"></a>**Set-AzureRmApiManagementUser**
- Parameter "Password" akan diganti untuk mendukung SecureString

```powershell-interactive
# Old
Set-AzureRmApiManagementUser [other required parameters] -Password "plain-text string"

# New
Set-AzureRmApiManagementUser [other required parameters] -Password $SecureStringVariable
```

## <a name="breaking-changes-to-batch-cmdlets"></a>Memutus perubahan ke cmdlet Kumpulan

### <a name="new-azurebatchcertificate"></a>**New-AzureBatchCertificate**
- Parameter `Password` sedang diganti agar menghasilkan string Aman

```powershell-interactive
# Old
New-AzureBatchCertificate [other required parameters] -Password "plain-text string"

# New
New-AzureBatchCertificate [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurebatchcomputenodeuser"></a>**New-AzureBatchComputeNodeUser**
- Parameter `Password` sedang diganti agar menghasilkan string Aman

```powershell-interactive
# Old
New-AzureBatchComputeNodeUser [other required parameters] -Password "plain-text string"

# New
New-AzureBatchComputeNodeUser [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermbatchcomputenodeuser"></a>**Set-AzureRmBatchComputeNodeUser**
- Parameter `Password` sedang diganti agar menghasilkan string Aman

```powershell-interactive
# Old
Set-AzureRmBatchComputeNodeUser [other required parameters] -Password "plain-text string"

# New
Set-AzureRmBatchComputeNodeUser [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurebatchtask"></a>**New-AzureBatchTask**
 - Menghapus `RunElevated` sakelar dan menggantinya dengan `UserIdentity` .

```powershell-interactive
# Old
New-AzureBatchTask -Id $taskId1 -JobId $jobId -CommandLine "cmd /c echo hello" -RunElevated $TRUE

# New
$autoUser = New-Object Microsoft.Azure.Commands.Batch.Models.PSAutoUserSpecification -ArgumentList @("Task", "Admin")
$userIdentity = New-Object Microsoft.Azure.Commands.Batch.Models.PSUserIdentity $autoUser
New-AzureBatchTask -Id $taskId1 -JobId $jobId -CommandLine "cmd /c echo hello" -UserIdentity $userIdentity
```

Hal ini juga memengaruhi properti `RunElevated` pada , , , , dan `PSCloudTask` `PSStartTask` `PSJobManagerTask` `PSJobPreparationTask` `PSJobReleaseTask` .

### <a name="psmultiinstancesettings"></a>**PSMultiInstanceSettings**

- `PSMultiInstanceSettings` constructor tidak lagi mengambil parameter yang `numberOfInstances` diperlukan, sebaliknya dibutuhkan `coordinationCommandLine` parameter.

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
 - Menghapus `RunElevated` properti pada `PSCloudTask` . Properti `UserIdentity` telah ditambahkan untuk menggantikan `RunElevated` .

```powershell-interactive
# Old
$task = Get-AzureBatchTask [parameters]
$task.RunElevated

# New
$task = Get-AzureBatchTask [parameters]
$task.UserIdentity.AutoUser.ElevationLevel
```

Hal ini juga memengaruhi properti `RunElevated` pada , , , , dan `PSCloudTask` `PSStartTask` `PSJobManagerTask` `PSJobPreparationTask` `PSJobReleaseTask` .

### <a name="multiple-types"></a>**Beberapa tipe**

- Mengganti nama `SchedulingError` properti menjadi `PSExitConditions` `PreProcessingError` .

```powershell-interactive
# Old
$task = Get-AzureBatchTask [parameters]
$task.ExitConditions.SchedulingError

# New
$task = Get-AzureBatchTask [parameters]
$task.ExitConditions.PreProcessingError
```

### <a name="multiple-types"></a>**Beberapa tipe**

- Mengganti nama `SchedulingError` properti pada , , , , dan menjadi `PSJobPreparationTaskExecutionInformation` `PSJobReleaseTaskExecutionInformation` `PSStartTaskInformation` `PSSubtaskInformation` `PSTaskExecutionInformation` `FailureInformation` .
  - `FailureInformation` akan dikembalikan kapan pun terdapat kegagalan tugas. Ini mencakup semua kasus kesalahan penjadwalan sebelumnya, serta kode keluar tugas bukan nol, dan kegagalan unggahan file dari fitur file output baru.
  - Struktur ini sama seperti sebelumnya sehingga tidak ada perubahan kode yang diperlukan saat menggunakan tipe ini.

```powershell-interactive
# Old
$task = Get-AzureBatchTask [parameters]
$task.ExecutionInformation.SchedulingError

# New
$task = Get-AzureBatchTask [parameters]
$task.ExecutionInformation.FailureInformation
```

Hal ini juga terjadi: Get-AzureBatchPool, Get-AzureBatchSubtask, Get-AzureBatchJobPreparationAndReleaseTaskStatus

### <a name="new-azurebatchpool"></a>**New-AzureBatchPool**
 - Dihapus `TargetDedicated` dan diganti dengan dan `TargetDedicatedComputeNodes` `TargetLowPriorityComputeNodes` .
 - `TargetDedicatedComputeNodes` memiliki alias `TargetDedicated` .

```powershell-interactive
# Old
New-AzureBatchPool [other parameters] [-TargetDedicated <Int32>]

# New
New-AzureBatchPool [other parameters] [-TargetDedicatedComputeNodes <Int32>] [-TargetLowPriorityComputeNodes <Int32>]
```

Hal ini juga berdampak pada: Start-AzureBatchPoolResize

### <a name="get-azurebatchpool"></a>**Get-AzureBatchPool**
 - Mengganti nama `TargetDedicated` dan properti pada untuk dan `CurrentDedicated` `PSCloudPool` `TargetDedicatedComputeNodes` `CurrentDedicatedComputeNodes` .

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

- Diganti `ResizeError` `ResizeErrors` namanya `PSCloudPool` menjadi pada , dan kini menjadi koleksi.

```powershell-interactive
# Old
$pool = Get-AzureBatchPool [parameters]
$pool.ResizeError

# New
$pool = Get-AzureBatchPool [parameters]
$pool.ResizeErrors[0]
```

### <a name="new-azurebatchjob"></a>**New-AzureBatchJob**
- Mengganti nama `TargetDedicated` properti menjadi `PSPoolSpecification` `TargetDedicatedComputeNodes` .

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
 - Dihapus `Name` dan diganti dengan `Path` .
 - `Path` memiliki alias `Name` .

```powershell-interactive
# Old
Get-AzureBatchNodeFile [other parameters] [[-Name] <String>]

# New
Get-AzureBatchNodeFile [other parameters] [[-Path] <String>]
```

Hal ini juga memengaruhi: Get-AzureBatchNodeFileContent, Remove-AzureBatchNodeFile

### <a name="type-psnodefile"></a>Ketik **PSNodeFile**

 - Mengganti nama `Name` properti menjadi `PSNodeFile` `Path` .

```powershell-interactive
# Old
$file = Get-AzureBatchNodeFile [parameters]
$file.Name

# New
$file = Get-AzureBatchNodeFile [parameters]
$file.Path
```

### <a name="get-azurebatchsubtask"></a>**Get-AzureBatchSubtask**
- Properti `PreviousState` `State` dan bukan lagi tipe , `PSSubtaskInformation` bukan `TaskState` `SubtaskState` tipe.
  - Tidak `TaskState` `SubtaskState` seperti , tidak memiliki `Active` nilai, karena tidak mungkin subtugas untuk berada dalam `Active` keadaan tertentu.

```powershell-interactive
# Old
$subtask = Get-AzureBatchSubtask [parameters]
if ($subtask.State -eq Microsoft.Azure.Batch.Common.TaskState.Running) { }

# New
$subtask = Get-AzureBatchSubtask [parameters]
if ($subtask.State -eq Microsoft.Azure.Batch.Common.SubtaskState.Running) { }
```

## <a name="breaking-changes-to-compute-cmdlets"></a>Memutus perubahan pada Cmdlet Perhitungan

### <a name="set-azurermvmaccessextension"></a>**Set-AzureRmVMAccessExtension**
- Parameter "UserName" dan "Password" akan diganti untuk mendukung PSCredential

```powershell-interactive
# Old
Set-AzureRmVMAccessExtension [other required parameters] -UserName "plain-text string" -Password "plain-text string"

# New
Set-AzureRmVMAccessExtension [other required parameters] -Credential $PSCredential
```

## <a name="breaking-changes-to-eventhub-cmdlets"></a>Memutus perubahan pada cmdlet EventHub

### <a name="new-azurermeventhubnamespaceauthorizationrule"></a>**New-AzureRmEventHubNamespaceAuthorizationRule**
- Cmdlet 'New-AzureRmEventHubNamespaceAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'New-AzureRmEventHubAuthorizationRule'

### <a name="get-azurermeventhubnamespaceauthorizationrule"></a>**Get-AzureRmEventHubNamespaceAuthorizationRule**
- Cmdlet 'Get-AzureRmEventHubNamespaceAuthorizationRule' telah dihapus. Harap gunakan cmdlet 'Get-AzureRmEventHubAuthorizationRule'

### <a name="set-azurermeventhubnamespaceauthorizationrule"></a>**Set-AzureRmEventHubNamespaceAuthorizationRule**
- Cmdlet 'Set-AzureRmEventHubNamespaceAuthorizationRule' telah dihapus. Harap gunakan cmdlet 'Set-AzureRmEventHubAuthorizationRule'

### <a name="remove-azurermeventhubnamespaceauthorizationrule"></a>**Remove-AzureRmEventHubNamespaceAuthorizationRule**
- Cmdlet 'Remove-AzureRmEventHubNamespaceAuthorizationRule' telah dihapus. Harap gunakan cmdlet 'Remove-AzureRmEventHubAuthorizationRule'

### <a name="new-azurermeventhubnamespacekey"></a>**New-AzureRmEventHubNamespaceKey**
- Cmdlet 'New-AzureRmEventHubNamespaceKey' telah dihapus. Harap gunakan cmdlet 'New-AzureRmEventHubKey'

### <a name="get-azurermeventhubnamespacekey"></a>**Get-AzureRmEventHubNamespaceKey**
- Cmdlet 'Get-AzureRmEventHubNamespaceKey' telah dihapus. Harap gunakan cmdlet 'Get-AzureRmEventHubKey'

### <a name="new-azurermeventhubnamespace"></a>**New-AzureRmEventHubNamespace**
- Properti 'Status' dan 'Diaktifkan' dari NamespceAttributes akan dihapus.

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
- Properti 'Status' dan 'Diaktifkan' dari NamespceAttributes akan dihapus.

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
- Properti 'Status' dan 'Diaktifkan' dari NamespceAttributes akan dihapus.

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

## <a name="breaking-changes-to-insights-cmdlets"></a>Memutus perubahan pada Insights cmdlet

### <a name="add-azurermlogalertrule"></a>**Add-AzureRMLogAlertRule**
- Cmdlet **Add-AzureRMLogAlertRule** telah tidak berlaku
- Setelah 1 Oktober menggunakan cmdlet ini tidak akan berpengaruh lagi karena fungsionalitas ini akan dialihkan ke Peringatan Log Aktivitas. Silakan lihat https://aka.ms/migratemealerts informasi selengkapnya.

### <a name="get-azurermusage"></a>**Get-AzureRMUsage**
- Cmdlet **Get-AzureRMUsage** telah tidak berlaku lagi

### <a name="get-azurermalerthistory--get-azurermautoscalehistory--get-azurermlogs"></a>**Get-AzureRmAlertHistory** / **Get-AzureRmAutoscaleHistory** / **Get-AzureRmLogs**
- Perubahan output: Bidang EventChannels dari objek EventData (dikembalikan oleh cmdlet ini) akan disusinggasi karena sekarang mengembalikan nilai konstanta (Admin,Operasi.)

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
- Perubahan output: Bidang AutoscaleSettingResourceName akan ditolak karena bidang ini selalu sama dengan bidang Nama.

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
- Perubahan output: Tipe output akan berubah untuk mengembalikan objek tunggal yang berisi ID permintaan dan kode status.

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

## <a name="breaking-changes-to-network-cmdlets"></a>Memutus perubahan ke cmdlet Jaringan

### <a name="add-azurermapplicationgatewaysslcertificate"></a>**Add-AzureRmApplicationGatewaySslCertificate**
- Parameter "Password" akan diganti untuk mendukung SecureString

```powershell-interactive
# Old
Add-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password "plain-text string"

# New
Add-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermapplicationgatewaysslcertificate"></a>**New-AzureRmApplicationGatewaySslCertificate**
- Parameter "Password" akan diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password "plain-text string"

# New
New-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermapplicationgatewaysslcertificate"></a>**Set-AzureRmApplicationGatewaySslCertificate**
- Parameter "Password" akan diganti untuk mendukung SecureString

```powershell-interactive
# Old
Set-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password "plain-text string"

# New
Set-AzureRmApplicationGatewaySslCertificate [other required parameters] -Password $SecureStringVariable
```

## <a name="breaking-changes-to-resources-cmdlets"></a>Memutus perubahan ke cmdlet Sumber Daya

### <a name="new-azurermadappcredential"></a>**New-AzureRmADAppCredential**
- Parameter "Password" akan diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmADAppCredential [other required parameters] -Password "plain-text string"

# New
New-AzureRmADAppCredential [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermadapplication"></a>**Aplikasi New-AzureRmAD**
- Parameter "Password" akan diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmADApplication [other required parameters] -Password "plain-text string"

# New
New-AzureRmADApplication [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermadserviceprincipal"></a>**New-AzureRmADServicePrincipal**
- Parameter "Password" akan diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmADServicePrincipal [other required parameters] -Password "plain-text string"

# New
New-AzureRmADServicePrincipal [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermadspcredential"></a>**New-AzureRmADSpCredential**
- Parameter "Password" akan diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmADSpCredential [other required parameters] -Password "plain-text string"

# New
New-AzureRmADSpCredential [other required parameters] -Password $SecureStringVariable
```

### <a name="new-azurermaduser"></a>**New-AzureRmADUser**
- Parameter "Password" akan diganti untuk mendukung SecureString

```powershell-interactive
# Old
New-AzureRmADUser [other required parameters] -Password "plain-text string"

# New
New-AzureRmADUser [other required parameters] -Password $SecureStringVariable
```

### <a name="set-azurermaduser"></a>**Set-AzureRmADUser**
- Parameter "Password" akan diganti untuk mendukung SecureString

```powershell-interactive
# Old
Set-AzureRmADUser [other required parameters] -Password "plain-text string"

# New
Set-AzureRmADUser [other required parameters] -Password $SecureStringVariable
```

## <a name="breaking-changes-to-servicebus-cmdlets"></a>Memutus perubahan pada cmdlet ServiceBus

### <a name="get-azurermservicebustopicauthorizationrule"></a>**Get-AzureRmServiceBusTopicAuthorizationRule**
- Cmdlet 'Get-AzureRmServiceBusTopicAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'Get-AzureRmServiceBusAuthorizationRule'.

### <a name="get-azurermservicebustopickey"></a>**Get-AzureRmServiceBusTopicKey**
- Cmdlet 'Get-AzureRmServiceBusTopicKey' telah dihapus. Silakan gunakan cmdlet 'Get-AzureRmServiceBusKey'.

### <a name="new-azurermservicebustopicauthorizationrule"></a>**New-AzureRmServiceBusTopicAuthorizationRule**
- Cmdlet 'New-AzureRmServiceBusTopicAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'New-AzureRmServiceBusAuthorizationRule'.

### <a name="new-azurermservicebustopickey"></a>**New-AzureRmServiceBusTopicKey**
- Cmdlet 'New-AzureRmServiceBusTopicKey' telah dihapus. Silakan gunakan cmdlet 'New-AzureRmServiceBusKey'.

### <a name="remove-azurermservicebustopicauthorizationrule"></a>**Remove-AzureRmServiceBusTopicAuthorizationRule**
- Cmdlet 'Remove-AzureRmServiceBusTopicAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'Remove-AzureRmServiceBusAuthorizationRule'.

### <a name="set-azurermservicebustopicauthorizationrule"></a>**Set-AzureRmServiceBusTopicAuthorizationRule**
- Cmdlet 'Set-AzureRmServiceBusTopicAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'Set-AzureRmServiceBusAuthorizationRule'.

### <a name="new-azurermservicebusnamespacekey"></a>**New-AzureRmServiceBusNamespaceKey**
- Cmdlet 'New-AzureRmServiceBusNamespaceKey' telah dihapus. Silakan gunakan cmdlet 'New-AzureRmServiceBusKey'.

### <a name="get-azurermservicebusqueueauthorizationrule"></a>**Get-AzureRmServiceBusQueueAuthorizationRule**
- Cmdlet 'Get-AzureRmServiceBusQueueAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'Get-AzureRmServiceBusAuthorizationRule'.

### <a name="get-azurermservicebusqueuekey"></a>**Get-AzureRmServiceBusQueueKey**
- Cmdlet 'Get-AzureRmServiceBusQueueKey' telah dihapus. Silakan gunakan cmdlet 'Get-AzureRmServiceBusKey'.

### <a name="new-azurermservicebusqueueauthorizationrule"></a>**New-AzureRmServiceBusQueueAuthorizationRule**
- Cmdlet 'New-AzureRmServiceBusQueueAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'New-AzureRmServiceBusAuthorizationRule'.

### <a name="new-azurermservicebusqueuekey"></a>**New-AzureRmServiceBusQueueKey**
- Cmdlet 'New-AzureRmServiceBusQueueKey' telah dihapus. Silakan gunakan cmdlet 'New-AzureRmServiceBusKey'.

### <a name="remove-azurermservicebusqueueauthorizationrule"></a>**Remove-AzureRmServiceBusQueueAuthorizationRule**
- Cmdlet 'Remove-AzureRmServiceBusQueueAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'GRemove-AzureRmServiceBusAuthorizationRule'.

### <a name="set-azurermservicebusqueueauthorizationrule"></a>**Set-AzureRmServiceBusQueueAuthorizationRule**
- Cmdlet 'Set-AzureRmServiceBusQueueAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'Set-AzureRmServiceBusAuthorizationRule'.

### <a name="get-azurermservicebusnamespaceauthorizationrule"></a>**Get-AzureRmServiceBusNamespaceAuthorizationRule**
- Cmdlet 'Get-AzureRmServiceBusNamespaceAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'Get-AzureRmServiceBusAuthorizationRule'.

### <a name="get-azurermservicebusnamespacekey"></a>**Get-AzureRmServiceBusNamespaceKey**
- Cmdlet 'Get-AzureRmServiceBusNamespaceKey' telah dihapus. Silakan gunakan cmdlet 'Get-AzureRmServiceBusKey'.

### <a name="new-azurermservicebusnamespaceauthorizationrule"></a>**New-AzureRmServiceBusNamespaceAuthorizationRule**
- Cmdlet 'New-AzureRmServiceBusNamespaceAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'New-AzureRmServiceBusAuthorizationRule'.

### <a name="remove-azurermservicebusnamespaceauthorizationrule"></a>**Remove-AzureRmServiceBusNamespaceAuthorizationRule**
- Cmdlet 'Remove-AzureRmServiceBusNamespaceAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'Remove-AzureRmServiceBusAuthorizationRule'.

### <a name="set-azurermservicebusnamespaceauthorizationrule"></a>**Set-AzureRmServiceBusNamespaceAuthorizationRule**
- Cmdlet 'Set-AzureRmServiceBusNamespaceAuthorizationRule' telah dihapus. Silakan gunakan cmdlet 'Set-AzureRmServiceBusAuthorizationRule'.

### <a name="type-namespaceattributes"></a>**Ketik NamespaceAttributes**
- Properti berikut ini telah dihapus
    - Diaktifkan
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
- Properti berikut ini ditandai sebagai sudah tidak t obsolete:
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
- Properti berikut ini ditandai sebagai sudah tidak t obsolete:
    - Lokasi
    - IsExpress
    - IsAnonymousAccessible
    - PemfilteranMessagesBeforePublishing
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
- Properti berikut ini ditandai sebagai sudah tidak t obsolete
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
