---
title: Panduan migrasi untuk Az 6.0.0
description: Panduan migrasi ini berisi daftar perubahan terbaru yang dibuat Azure PowerShell rilis Az versi 6.0.0.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/07/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 0724e8c0d002fa0c5c79cd60e62971e987db464e
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429487"
---
# <a name="migration-guide-for-az-600"></a>Panduan Migrasi untuk Az 6.0.0

Dokumen ini menjelaskan perubahan antara versi 5.0.0 dan 6.0.0 az.

- [Panduan Migrasi untuk Az 6.0.0](#migration-guide-for-az-600)
    - [Versi PowerShell yang didukung](#supported-versions-of-powershell)
    - [Az.Accounts](#azaccounts)
        - [`Connect-AzAccount`](#connect-azaccount)
    - [Az.ContainerInstance](#azcontainerinstance)
        - [`New-AzContainerGroup`](#new-azcontainergroup)
        - [`Remove-AzContainerGroup`](#remove-azcontainergroup)
        - [`Get-AzContainerGroup`](#get-azcontainergroup)
        - [`Get-AzContainerInstanceLog`](#get-azcontainerinstancelog)
    - [Az.DesktopVirtualization](#azdesktopvirtualization)
        - [`New-AzWvdHostPool`](#new-azwvdhostpool)
        - [`Expand-AzWvdMsixImage`](#expand-azwvdmsiximage)
        - [`New-AzWvdMsixPackage`](#new-azwvdmsixpackage)
        - [`Update-AzWvdHostPool`](#update-azwvdhostpool)
    - [Az.StreamAnalytics](#azstreamanalytics)
        - [`Get-AzStreamAnalyticsDefaultFunctionDefinition`](#get-azstreamanalyticsdefaultfunctiondefinition)
        - [`New-AzStreamAnalyticsJob`](#new-azstreamanalyticsjob)
        - [`New-AzStreamAnalyticsTransformation`](#new-azstreamanalyticstransformation)
    - [Az.RecoveryServices](#azrecoveryservices)
        - [`Set-AzRecoveryServicesBackupProperty`](#set-azrecoveryservicesbackupproperty)
        - [`Get-AzRecoveryServicesBackupJobDetail`](#get-azrecoveryservicesbackupjobdetail)
    - [Az.Storage](#azstorage)
        - [`Remove-AzRmStorageShare`](#remove-azrmstorageshare)
    - [az.servicefabric](#azservicefabric)
        - [`Add-AzServiceFabricClusterCertificate`](#add-azservicefabricclustercertificate)
        - [`Get-AzServiceFabricManagedClusterService`](#get-azservicefabricmanagedclusterservice)
        - [`New-AzServiceFabricManagedCluster`](#new-azservicefabricmanagedcluster)
        - [`New-AzServiceFabricManagedClusterService`](#new-azservicefabricmanagedclusterservice)
        - [`Remove-AzServiceFabricClusterCertificate`](#remove-azservicefabricclustercertificate)
        - [`Remove-AzServiceFabricManagedClusterService`](#remove-azservicefabricmanagedclusterservice)
        - [`Set-AzServiceFabricManagedCluster`](#set-azservicefabricmanagedcluster)
        - [`Set-AzServiceFabricManagedClusterService`](#set-azservicefabricmanagedclusterservice)

## <a name="supported-versions-of-powershell"></a>Versi PowerShell yang didukung

Karena [VBA-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701) Az 6 hanya didukung pada platform berikut:
- PowerShell 7.1: versi 7.1.3 atau lebih baru
- PowerShell 7.0: versi 7.0.6 atau lebih baru
- Windows PowerShell 5.1

Untuk detail selengkapnya, lihat siklus [Azure PowerShell dukungan baru](https://aka.ms/azpslifecycle)

## <a name="azaccounts"></a>Az.Accounts

### `Connect-AzAccount`

Menghapus parameter yang sudah tidak t obsolete ManagedServiceHostName, ManagedServicePort dan ManagedServiceSecret.

#### <a name="before"></a>Sebelum

```powershell
Connect-AzAccount -Identity -ManagedServiceSecret $secret
```
#### <a name="after"></a>Setelah

```powershell
#To use customized MSI endpoint, please set environment variable MSI_ENDPOINT, e.g. "http://localhost:50342/oauth2/token"; to use customized MSI secret, please set environment variable MSI_SECRET.
Connect-AzAccount -Identity
```
## <a name="azcontainerinstance"></a>Az.ContainerInstance

### `New-AzContainerGroup`

Tidak lagi mendukung parameter , , , , , , , , , , , , , , , dan tidak ada `Image` alias yang `RegistryCredential` ditemukan untuk nama `AzureFileVolumeShareName` `AzureFileVolumeAccountCredential` `AzureFileVolumeMountPath` `IdentityId` parameter `AssignIdentity` `OsType` `Cpu` `MemoryInGB` `IpAddressType` `DnsNameLabel` `Port` `Command` `EnvironmentVariable` `RegistryServerDomain` asli.

#### <a name="before"></a>Sebelum

```powershell
PS C:\> New-AzContainerGroup -ResourceGroupName demo -Name mycontainer -Image nginx -OsType Linux -IpAddressType Public -Port @(8000)

ResourceGroupName        : demo
Id                       : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/demo/providers/Microsoft.ContainerInstance/containerGroups/mycontainer
Name                     : mycontainer
Type                     : Microsoft.ContainerInstance/containerGroups
Location                 : westus
Tags                     :
ProvisioningState        : Creating
Containers               : {mycontainer}
ImageRegistryCredentials :
RestartPolicy            :
IpAddress                : 13.88.10.240
Ports                    : {8000}
OsType                   : Linux
Volumes                  :
State                    : Running
Events                   : {}
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> $port1 = New-AzContainerInstancePortObject -Port 8000 -Protocol TCP
PS C:\> $port2 = New-AzContainerInstancePortObject -Port 8001 -Protocol TCP
PS C:\> $container = New-AzContainerInstanceObject -Name test-container -Image nginx -RequestCpu 1 -RequestMemoryInGb 1.5 -Port @($port1, $port2)
PS C:\> $containerGroup = New-AzContainerGroup -ResourceGroupName test-rg -Name test-cg -Location eastus -Container $container -OsType Linux -RestartPolicy "Never" -IpAddressType Public

Location Name    Type
-------- ----    ----
eastus   test-cg Microsoft.ContainerInstance/containerGroups
```
### `Remove-AzContainerGroup`

Cmdlet 'Remove-AzContainerGroup' tidak lagi mendukung parameter 'ResourceId' dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelum

```powershell
PS C:\> Find-AzResource -ResourceGroupEquals MyResourceGroup -ResourceNameEquals MyContainer | Remove-AzContainerGroup
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> Remove-AzContainerGroup -Name test-cg -ResourceGroupName test-rg

Location Name    Type
-------- ----    ----
eastus   test-cg Microsoft.ContainerInstance/containerGroups
```

### `Get-AzContainerGroup`

Cmdlet 'Get-AzContainerGroup' tidak lagi mendukung parameter 'ResourceId' dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelum

```powershell
PS C:\> Find-AzResource -ResourceGroupEquals demo -ResourceNameEquals mycontainer | Get-AzContainerGroup

ResourceGroupName        : demo
Id                       : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/demo/providers/Microsoft.ContainerInstance/containerGroups/mycontainer
Name                     : mycontainer
Type                     : Microsoft.ContainerInstance/containerGroups
Location                 : westus
Tags                     :
ProvisioningState        : Succeeded
Containers               : {mycontainer}
ImageRegistryCredentials :
RestartPolicy            :
IpAddress                : 13.88.10.240
Ports                    : {8000}
OsType                   : Linux
Volumes                  :
State                    : Running
Events                   : {}
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> Get-AzContainerGroup

Location Name           Type
-------- ----           ----
eastus   bez-cg1         Microsoft.ContainerInstance/containerGroups
eastus   bez-cg2        Microsoft.ContainerInstance/containerGroups
```

### `Get-AzContainerInstanceLog`

Cmdlet 'Get-AzContainerInstanceLog' tidak lagi mendukung parameter 'ResourceId' dan tidak ada alias yang ditemukan untuk nama parameter asli.
Cmdlet 'Get-AzContainerInstanceLog' tidak lagi mendukung parameter 'Name' dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelum

```powershell
PS C:\> Get-AzContainerGroup -ResourceGroupName demo -Name mycontainer | Get-AzContainerInstanceLog

Log line 1.
Log line 2.
Log line 3.
Log line 4.
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> Get-AzContainerInstanceLog -ContainerGroupName test-cg -ContainerName test-container -ResourceGroupName test-rg
```

## <a name="azdesktopvirtualization"></a>Az.DesktopVirtualization

### `New-AzWvdHostPool`

Cmdlet 'New-AzWvdHostPool' tidak lagi mendukung parameter 'SsoContext' dan tidak ada alias yang ditemukan untuk nama parameter asli.

### `Expand-AzWvdMsixImage`

Cmdlet 'Expand-AzWvdMsixImage' tidak lagi mendukung tipe 'Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20201102Preview.IMsixImageUri' untuk parameter 'MsixImageUri'.

#### <a name="before"></a>Sebelum

```powershell
$MsixImageUri = [Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20201102Preview.IMsixImageUri]::New()
Get-AzWvdDesktop -ResourceGroupName ResourceGroupName -ApplicationGroupName ApplicationGroupName -Name DesktopName | Expand-AzWvdMsixImage -MsixImageUri $MsixImageUri
```

#### <a name="after"></a>Setelah

```powershell
$MsixImageUri = [Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210201Preview.IMsixImageUri]::New()
Get-AzWvdDesktop -ResourceGroupName ResourceGroupName -ApplicationGroupName ApplicationGroupName -Name DesktopName | Expand-AzWvdMsixImage -MsixImageUri $MsixImageUri
```

### `New-AzWvdMsixPackage`

Tipe elemen untuk parameter 'PackageApplication' telah diubah dari 'Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20201102Preview.IMsixPackageApplications' menjadi 'Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210201Preview.IMsixPackageApplications'.
Tipe elemen untuk parameter 'PackageDependency' telah diubah dari 'Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20201102Preview.IMsixPackageDependencies' menjadi 'Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210201Preview.IMsixPackageDependencies'.

#### <a name="before"></a>Sebelum

```powershell
PS C:\> $apps = @([Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20201102Preview.IMsixPackageApplications]::New())
PS C:\> $deps = @([Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20201102Preview.IMsixPackageDependencies]::New())
PS C:\> New-AzWvdMsixPackage -FullName PackageFullName `
                            -HostPoolName HostPoolName `
                            -ResourceGroupName ResourceGroupName `
                            -SubscriptionId SubscriptionId `
                            -DisplayName displayname `
                            -ImagePath imageURI `
                            -IsActive:$false `
                            -IsRegularRegistration:$false `
                            -LastUpdated datelastupdated `
                            -PackageApplication $apps `
                            -PackageDependency $deps `
                            -PackageFamilyName packagefamilyname `
                            -PackageName packagename `
                            -PackageRelativePath packagerelativepath `
                            -Version packageversion `
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> $apps = @([Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210201Preview.IMsixPackageApplications]::New())
PS C:\> $deps = @([Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210201Preview.IMsixPackageDependencies]::New())
PS C:\> New-AzWvdMsixPackage -FullName PackageFullName `
                            -HostPoolName HostPoolName `
                            -ResourceGroupName ResourceGroupName `
                            -SubscriptionId SubscriptionId `
                            -DisplayName displayname `
                            -ImagePath imageURI `
                            -IsActive:$false `
                            -IsRegularRegistration:$false `
                            -LastUpdated datelastupdated `
                            -PackageApplication $apps `
                            -PackageDependency $deps `
                            -PackageFamilyName packagefamilyname `
                            -PackageName packagename `
                            -PackageRelativePath packagerelativepath `
                            -Version packageversion `
```

### `Update-AzWvdHostPool`

Cmdlet 'Update-AzWvdHostPool' tidak lagi mendukung parameter 'SsoContext' dan tidak ada alias yang ditemukan untuk nama parameter asli.

## <a name="azstreamanalytics"></a>Az.StreamAnalytics

### `Get-AzStreamAnalyticsDefaultFunctionDefinition`

Cmdlet 'Get-AzStreamAnalyticsDefaultFunctionDefinition' tidak lagi mendukung parameter 'File' dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelum

```powershell
Get-AzStreamAnalyticsDefaultFunctionDefinition -ResourceGroupName "StreamAnalytics-Default-West-US" -JobName "StreamJob22" -File "C:\RetrieveDefaultDefinitionRequest.json" -Name "ScoreTweet"
```

#### <a name="after"></a>Setelah

```powershell
Get-AzStreamAnalyticsDefaultFunctionDefinition -ResourceGroupName azure-rg-test -JobName sajob-01-pwsh -Name mlsfunction-01 -BindingType Microsoft.MachineLearningServices -Endpoint "http://875da830-4d5f-44f1-b221-718a5f26a21d.eastus.azurecontainer.io/score"-UdfType Scalar
Input is specified in flattened parameters instead from the input file.
```

### `New-AzStreamAnalyticsJob`

Cmdlet 'New-AzStreamAnalyticsJob' tidak lagi mendukung parameter 'File' dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelum

```powershell
New-AzStreamAnalyticsJob -ResourceGroupName "StreamAnalytics-Default-West-US" -File "C:\JobDefinition.json"
```

#### <a name="after"></a>Setelah

```powershell
New-AzStreamAnalyticsJob -ResourceGroupName azure-rg-test -Name sajob-02-pwsh -Location westcentralus -SkuName Standard
Input is specified in flattened parameters instead from the input file.
```

### `New-AzStreamAnalyticsTransformation`

Cmdlet 'New-AzStreamAnalyticsTransformation' tidak lagi mendukung parameter 'File' dan tidak ada alias yang ditemukan untuk nama parameter asli.

#### <a name="before"></a>Sebelum

```powershell
New-AzStreamAnalyticsTransformation -ResourceGroupName "StreamAnalytics-Default-West-US" -File "C:\Transformation.json" -JobName "StreamingJob" -Name "StreamingJobTransform"
```

#### <a name="after"></a>Setelah

```powershell
New-AzStreamAnalyticsTransformation -ResourceGroupName azure-rg-test -JobName sajob-01-pwsh -Name tranf-01 -StreamingUnit 6 -Query "Select Id, Name from input-01"
Input is specified in flattened parameters instead from the input file.
```

## <a name="azrecoveryservices"></a>Az.RecoveryServices

### `Set-AzRecoveryServicesBackupProperty`

Dihapus Set-AzRecoveryServicesBackupProperties alias jamak, Set-AzRecoveryServicesBackupProperty cmdlet setelahnya

### `Get-AzRecoveryServicesBackupJobDetail`

Dihapus Get-AzRecoveryServicesBackupJobDetails alias jamak, Get-AzRecoveryServicesBackupJobDetail cmdlet setelahnya

#### <a name="before"></a>Sebelum

```powershell
$jobDetails = Get-AzRecoveryServicesBackupJobDetails -VaultId $vault.ID -Job $job
$jobDetails2 = Get-AzRecoveryServicesBackupJobDetails -VaultId $vault.ID -JobId $job.JobId
```

#### <a name="after"></a>Setelah

```powershell
$jobDetails = Get-AzRecoveryServicesBackupJobDetail -VaultId $vault.ID -Job $job
$jobDetails2 = Get-AzRecoveryServicesBackupJobDetail -VaultId $vault.ID -JobId $job.JobId
```

## <a name="azstorage"></a>Az.Storage

### `Remove-AzRmStorageShare`

Cmdlet 'Remove-AzRmStorageShare' dapat menghapus berbagi dengan snapshot secara default sebelum; tapi setelah perubahan, berbagi dengan snapshot akan gagal secara default, perlu menambahkan parameter "-Sertakan Snapshot" untuk membuat keberhasilan.

#### <a name="before"></a>Sebelum

```powershell
Remove-AzRmStorageShare -ResourceGroupName $resourceGroupName -StorageAccountName $accountName -Name $shareName
```

#### <a name="after"></a>Setelah

```powershell
Remove-AzRmStorageShare -ResourceGroupName $resourceGroupName -StorageAccountName $accountName -Name $shareName -Force -Include Snapshots
```

## <a name="azservicefabric"></a>az.servicefabric

### `Add-AzServiceFabricClusterCertificate`

cmdlet ini telah dihapus sepenuhnya. ikuti instruksi di [sini](/azure/service-fabric/service-fabric-cluster-security-update-certs-azure#add-a-secondary-certificate-using-azure-resource-manager) untuk menambahkan sertifikat kluster.

### `Get-AzServiceFabricManagedClusterService`

Ubah model PSManagedService untuk menghindari penggunaan parameter properti secara langsung dari sdk. Sekarang semua properti berada di tingkat pertama objek.
Dan menghapus parameter yang sudah tidak berlaku InstanceCloseDelayDuration, DropSourceReplicaOnMove dan ServiceDnsName

#### <a name="before"></a>Sebelum

```powershell
$service = Get-AzServiceFabricManagedClusterService -ResourceId $resourceId
$statelessService.Properties.ProvisioningState
```

#### <a name="after"></a>Setelah

```powershell
$service = Get-AzServiceFabricManagedClusterService -ResourceId $resourceId
$statelessService.ProvisioningState
```

### `New-AzServiceFabricManagedCluster`

Menghapus parameter yang sudah tidak berlaku ReverseProxyEndpointPort.

### `New-AzServiceFabricManagedClusterService`

Ubah model PSManagedService untuk menghindari penggunaan parameter properti secara langsung dari sdk. Sekarang semua properti berada di tingkat pertama objek.
Dan menghapus parameter yang sudah tidak berlaku InstanceCloseDelayDuration, DropSourceReplicaOnMove dan ServiceDnsName

#### <a name="before"></a>Sebelum

```powershell
$service = New-AzServiceFabricManagedClusterService -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationName $appName -Name $serviceName -Type $serviceTypeName -Stateless -InstanceCount -1 -PartitionSchemaSingleton
$statelessService.Properties.ProvisioningState
```

#### <a name="after"></a>Setelah

```powershell
$service = New-AzServiceFabricManagedClusterService -ResourceGroupName $resourceGroupName -ClusterName $clusterName -ApplicationName $appName -Name $serviceName -Type $serviceTypeName -Stateless -InstanceCount -1 -PartitionSchemaSingleton
$statelessService.ProvisioningState
```

### `Remove-AzServiceFabricClusterCertificate`

cmdlet ini telah dihapus sepenuhnya. ikuti instruksi di [sini](/azure/service-fabric/service-fabric-cluster-security-update-certs-azure#remove-a-cluster-certificate-using-the-portal) untuk menambahkan sertifikat kluster.

### `Remove-AzServiceFabricManagedClusterService`

Ubah model PSManagedService untuk menghindari penggunaan parameter properti secara langsung dari sdk. Sekarang semua properti berada di tingkat pertama objek.

### `Set-AzServiceFabricManagedCluster`

Menghapus parameter yang sudah tidak berlaku ReverseProxyEndpointPort.

### `Set-AzServiceFabricManagedClusterService`

Ubah model PSManagedService untuk menghindari penggunaan parameter properti secara langsung dari sdk. Sekarang semua properti berada di tingkat pertama objek.
Dan menghapus parameter yang sudah tidak berlaku InstanceCloseDelayDuration, DropSourceReplicaOnMove dan ServiceDnsName

#### <a name="before"></a>Sebelum

```powershell
$service = Get-AzServiceFabricManagedClusterService -ResourceId $resourceId
$statelessService.Properties.MinInstanceCount = 3
service | Set-AzServiceFabricManagedClusterService
```

#### <a name="after"></a>Setelah

```powershell
$service = Get-AzServiceFabricManagedClusterService -ResourceId $resourceId
$statelessService.MinInstanceCount = 3
service | Set-AzServiceFabricManagedClusterService
```
