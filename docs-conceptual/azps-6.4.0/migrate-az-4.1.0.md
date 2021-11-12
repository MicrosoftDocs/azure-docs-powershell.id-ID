---
title: Panduan migrasi untuk Az 4.1.0
description: Panduan migrasi ini berisi daftar perubahan yang telah dibuat untuk Azure PowerShell di rilis Az versi 4.1.0.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/07/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 4a9a197830c81a1cf7055546f342b0a39ca38426
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429488"
---
# <a name="migration-guide-for-az-410"></a>Panduan Migrasi untuk Az 4.1.0

Dokumen ini menjelaskan perubahan antara versi 3.0.0 dan 4.1.0 az.

- [Panduan Migrasi untuk Az 4.1.0](#migration-guide-for-az-410)
  - [Az.ApiManagement](#azapimanagement)
    - [`Add-AzApiManagementRegion`](#add-azapimanagementregion)
    - [`New-AzApiManagement`](#new-azapimanagement)
    - [`Set-AzApiManagement`](#set-azapimanagement)
    - [`Get-AzApiManagementProperty`](#get-azapimanagementproperty)
    - [`New-AzApiManagementProperty`](#new-azapimanagementproperty)
    - [`Remove-AzApiManagementProperty`](#remove-azapimanagementproperty)
    - [`Set-AzApiManagementProperty`](#set-azapimanagementproperty)
  - [Az.Batch](#azbatch)
    - [`Get-AzBatchApplication`, `New-AzBatchApplication`](#get-azbatchapplication-new-azbatchapplication)
    - [`Get-AzBatchComputeNode`, `New-AzBatchPool`](#get-azbatchcomputenode-new-azbatchpool)
    - [`Get-AzBatchApplicationPackage`, `New-AzBatchApplicationPackage`](#get-azbatchapplicationpackage-new-azbatchapplicationpackage)
  - [Az.Compute](#azcompute)
    - [`Remove-AzVmssDiagnosticsExtension`](#remove-azvmssdiagnosticsextension)
    - [`Get-AzVMImage`](#get-azvmimage)
    - [`New-AzVMConfig`](#new-azvmconfig)
    - [`Update-AzVM`](#update-azvm)
    - [`New-AzProximityPlacementGroup`](#new-azproximityplacementgroup)
    - [`Remove-AzProximityPlacementGroup`](#remove-azproximityplacementgroup)
    - [`Get-AzProximityPlacementGroup`](#get-azproximityplacementgroup)
    - [`Add-AzVmssAdditionalUnattendContent`](#add-azvmssadditionalunattendcontent)
    - [`Add-AzVmssDataDisk`](#add-azvmssdatadisk)
    - [`Add-AzVmssExtension`](#add-azvmssextension)
    - [`Add-AzVmssNetworkInterfaceConfiguration`](#add-azvmssnetworkinterfaceconfiguration)
    - [`Add-AzVmssSecret`](#add-azvmsssecret)
    - [`Add-AzVmssSshPublicKey`](#add-azvmsssshpublickey)
    - [`Add-AzVmssWinRMListener`](#add-azvmsswinrmlistener)
    - [`New-AzVmssConfig`](#new-azvmssconfig)
    - [`Remove-AzVmssDataDisk`](#remove-azvmssdatadisk)
    - [`Remove-AzVmssExtension`](#remove-azvmssextension)
    - [`Remove-AzVmssNetworkInterfaceConfiguration`](#remove-azvmssnetworkinterfaceconfiguration)
    - [`Set-AzVmssBootDiagnostic`](#set-azvmssbootdiagnostic)
    - [`Set-AzVmssOsProfile`](#set-azvmssosprofile)
    - [`Set-AzVmssRollingUpgradePolicy`](#set-azvmssrollingupgradepolicy)
    - [`Set-AzVmssStorageProfile`](#set-azvmssstorageprofile)
    - [`New-AzVmss`](#new-azvmss)
    - [`Repair-AzVmssServiceFabricUpdateDomain`](#repair-azvmssservicefabricupdatedomain)
    - [`Get-AzVmss`](#get-azvmss)
    - [`Set-AzVmssOrchestrationServiceState`](#set-azvmssorchestrationservicestate)
    - [`Update-AzVmss`](#update-azvmss)
    - [`Add-AzVmssDiagnosticsExtension`](#add-azvmssdiagnosticsextension)
    - [`Disable-AzVmssDiskEncryption`](#disable-azvmssdiskencryption)
  - [Az.KeyVault](#azkeyvault)
    - [`New-AzKeyVaultCertificateOrganizationDetail`](#new-azkeyvaultcertificateorganizationdetail)
    - [`New-AzKeyVaultCertificateAdministratorDetail`](#new-azkeyvaultcertificateadministratordetail)
    - [`New-AzKeyVault`](#new-azkeyvault)
  - [Az.Monitor](#azmonitor)
    - [`Add-AzLogProfile`](#add-azlogprofile)
    - [`Get-AzLogProfile`](#get-azlogprofile)
    - [`New-AzMetricAlertRuleV2Criteria`](#new-azmetricalertrulev2criteria)
  - [Az.Network](#aznetwork)
    - [`Get-AzNetworkWatcherConnectionMonitor`](#get-aznetworkwatcherconnectionmonitor)
    - [`New-AzNetworkWatcherConnectionMonitorTestConfigurationObject`](#new-aznetworkwatcherconnectionmonitortestconfigurationobject)
  - [Az.OperationalInsights](#azoperationalinsights)
    - [`Get-AzOperationalInsightsDataSource`](#get-azoperationalinsightsdatasource)
    - [`New-AzOperationalInsightsApplicationInsightsDataSource`](#new-azoperationalinsightsapplicationinsightsdatasource)
    - [`New-AzOperationalInsightsAzureActivityLogDataSource`](#new-azoperationalinsightsazureactivitylogdatasource)
    - [`New-AzOperationalInsightsCustomLogDataSource`](#new-azoperationalinsightscustomlogdatasource)
    - [`New-AzOperationalInsightsLinuxPerformanceObjectDataSource`](#new-azoperationalinsightslinuxperformanceobjectdatasource)
    - [`New-AzOperationalInsightsLinuxSyslogDataSource`](#new-azoperationalinsightslinuxsyslogdatasource)
    - [`New-AzOperationalInsightsWindowsEventDataSource`](#new-azoperationalinsightswindowseventdatasource)
    - [`New-AzOperationalInsightsWindowsPerformanceCounterDataSource`](#new-azoperationalinsightswindowsperformancecounterdatasource)
    - [`Remove-AzOperationalInsightsDataSource`](#remove-azoperationalinsightsdatasource)
    - [`Disable-AzOperationalInsightsIISLogCollection`](#disable-azoperationalinsightsiislogcollection)
    - [`Disable-AzOperationalInsightsLinuxCustomLogCollection`](#disable-azoperationalinsightslinuxcustomlogcollection)
    - [`Disable-AzOperationalInsightsLinuxPerformanceCollection`](#disable-azoperationalinsightslinuxperformancecollection)
    - [`Disable-AzOperationalInsightsLinuxSyslogCollection`](#disable-azoperationalinsightslinuxsyslogcollection)
    - [`Enable-AzOperationalInsightsIISLogCollection`](#enable-azoperationalinsightsiislogcollection)
    - [`Enable-AzOperationalInsightsLinuxCustomLogCollection`](#enable-azoperationalinsightslinuxcustomlogcollection)
    - [`Enable-AzOperationalInsightsLinuxPerformanceCollection`](#enable-azoperationalinsightslinuxperformancecollection)
    - [`Enable-AzOperationalInsightsLinuxSyslogCollection`](#enable-azoperationalinsightslinuxsyslogcollection)
    - [`Get-AzOperationalInsightsSavedSearch`](#get-azoperationalinsightssavedsearch)
    - [`Get-AzOperationalInsightsSavedSearchResult`](#get-azoperationalinsightssavedsearchresult)
    - [`Get-AzOperationalInsightsSearchResult`](#get-azoperationalinsightssearchresult)
    - [`Get-AzOperationalInsightsStorageInsight`](#get-azoperationalinsightsstorageinsight)
    - [`New-AzOperationalInsightsStorageInsight`](#new-azoperationalinsightsstorageinsight)
    - [`Remove-AzOperationalInsightsStorageInsight`](#remove-azoperationalinsightsstorageinsight)
    - [`Set-AzOperationalInsightsStorageInsight`](#set-azoperationalinsightsstorageinsight)
    - [`Get-AzOperationalInsightsLinkTarget`](#get-azoperationalinsightslinktarget)
    - [`Get-AzOperationalInsightsWorkspace`](#get-azoperationalinsightsworkspace)
    - [`New-AzOperationalInsightsWorkspace`](#new-azoperationalinsightsworkspace)
    - [`Set-AzOperationalInsightsWorkspace`](#set-azoperationalinsightsworkspace)
    - [`Invoke-AzOperationalInsightsQuery`](#invoke-azoperationalinsightsquery)
  - [Az.Resources](#azresources)
    - [`Get-AzDeploymentScript`](#get-azdeploymentscript)
    - [`Get-AzDeploymentScriptLog`](#get-azdeploymentscriptlog)
    - [`Save-AzDeploymentScriptLog`](#save-azdeploymentscriptlog)
    - [`Get-AzResourceLock, New-AzResourceLock, Remove-AzResourceLock, Set-AzResourceLock`](#get-azresourcelock-new-azresourcelock-remove-azresourcelock-set-azresourcelock)
    - [`Get-AzPolicyAlias`](#get-azpolicyalias)
    - [`New-AzPolicyAssignment`](#new-azpolicyassignment)
    - [`Remove-AzDeploymentScript`](#remove-azdeploymentscript)
  - [Az.Storage](#azstorage)
    - [`Update-AzStorageAccountNetworkRuleSet`, `Get-AzStorageAccountNetworkRuleSet`](#update-azstorageaccountnetworkruleset-get-azstorageaccountnetworkruleset)
    - [`New-AzStorageTable`, `Get-AzStorageTable`](#new-azstoragetable-get-azstoragetable)
    - [`Get-AzStorageFile`, `Remove-AzStorageFile`, `Get-AzStorageFileContent`, `Set-AzStorageFileContent`, `Start-AzStorageFileCopy`](#get-azstoragefile-remove-azstoragefile-get-azstoragefilecontent-set-azstoragefilecontent-start-azstoragefilecopy)
    - [`Get-AzStorageFile`, `New-AzStorageDirectory`, `Remove-AzStorageDirectory`](#get-azstoragefile-new-azstoragedirectory-remove-azstoragedirectory)
    - [`Get-AzStorageShare`, `New-AzStorageShare`, `Remove-AzStorageShare`](#get-azstorageshare-new-azstorageshare-remove-azstorageshare)
    - [`Set-AzStorageShareQuota`](#set-azstoragesharequota)
    - [`Remove-AzStorageDirectory`](#remove-azstoragedirectory)

## <a name="azapimanagement"></a>Az.ApiManagement

### `Add-AzApiManagementRegion`

Tipe properti tipe `Type` telah berubah dari menjadi `Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementServiceIdentity` `Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementServiceIdentityType` `System.String` .

### `New-AzApiManagement`

- Cmdlet `New-AzApiManagement` tidak lagi mendukung parameter dan `AssignIdentity` tidak ada alias yang ditemukan untuk nama parameter aslinya.
- Kumpulan parameter `__AllParameterSets` untuk cmdlet telah `New-AzApiManagement` dihapus.

### `Set-AzApiManagement`

- Cmdlet `Set-AzApiManagement` tidak lagi mendukung parameter dan `AssignIdentity` tidak ada alias yang ditemukan untuk nama parameter aslinya.
- Kumpulan parameter `__AllParameterSets` untuk cmdlet telah `Set-AzApiManagement` dihapus.

### `Get-AzApiManagementProperty`

Cmdlet `Get-AzApiManagementProperty` telah digantikan oleh `Get-AzApiManagementNamedValue` .

### `New-AzApiManagementProperty`

Cmdlet `New-AzApiManagementProperty` telah digantikan oleh `New-AzApiManagementNamedValue` .

### `Remove-AzApiManagementProperty`

Cmdlet `Remove-AzApiManagementProperty` telah digantikan oleh `Remove-AzApiManagementNamedValue` .

### `Set-AzApiManagementProperty`

Cmdlet `Set-AzApiManagementProperty` telah digantikan oleh `Set-AzApiManagementNamedValue` .

## <a name="azbatch"></a>Az.Batch

### <a name="get-azbatchapplication-new-azbatchapplication"></a>`Get-AzBatchApplication`, `New-AzBatchApplication`

Properti `ApplicationPackages` tipe `Microsoft.Azure.Commands.Batch.Models.PSApplication` telah dihapus.

### <a name="get-azbatchcomputenode-new-azbatchpool"></a>`Get-AzBatchComputeNode`, `New-AzBatchPool`

Properti `PublicIPs` tipe `Microsoft.Azure.Commands.Batch.Models.PSNetworkConfiguration` telah dihapus

### <a name="get-azbatchapplicationpackage-new-azbatchapplicationpackage"></a>`Get-AzBatchApplicationPackage`, `New-AzBatchApplicationPackage`

Tipe properti tipe `StorageUrlExpiry` telah berubah dari menjadi `Microsoft.Azure.Commands.Batch.Models.PSApplicationPackage` `System.DateTime` `System.DateTime?` .

## <a name="azcompute"></a>Az.Compute

### `Remove-AzVmssDiagnosticsExtension`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Get-AzVMImage`

- Cmdlet `Get-AzVMImage` tidak lagi mendukung parameter dan `FilterExpression` tidak ada alias yang ditemukan untuk nama parameter aslinya.
- Kumpulan parameter `ListVMImage` untuk cmdlet telah `Get-AzVMImage` dihapus.

### `New-AzVMConfig`

- Cmdlet `New-AzVMConfig` tidak lagi mendukung parameter dan `AssignIdentity` tidak ada alias yang ditemukan untuk nama parameter aslinya.
- Kumpulan parameter `AssignIdentityParameterSet` untuk cmdlet telah `New-AzVMConfig` dihapus.

### `Update-AzVM`

- Cmdlet `Update-AzVM` tidak lagi mendukung parameter dan `AssignIdentity` tidak ada alias yang ditemukan untuk nama parameter aslinya.
- Kumpulan parameter `AssignIdentityParameterSet` untuk cmdlet telah `Update-AzVM` dihapus.

### `New-AzProximityPlacementGroup`

- Tipe generik untuk properti `VirtualMachines` , , dan telah diubah dari menjadi `VirtualMachineScaleSets` `AvailabilitySets` `System.Collections.Generic.IList1[Microsoft.Azure.Management.Compute.Models.SubResource]` `System.Collections.Generic.IList1[Microsoft.Azure.Management.Compute.Models.SubResourceWithColocationStatus]` .
- Properti `VirtualMachinesColocationStatus` , `VirtualMachineScaleSetsColocationStatus` , dan dari tipe `AvailabilitySetsColocationStatus` telah `Microsoft.Azure.Commands.Compute.Automation.Models.PSProximityPlacementGroup` dihapus.

#### <a name="before"></a>Sebelum

```powershell
PS C:\> New-AzProximityPlacementGroup -ResourceGroupName $resourceGroupName -Name $proximityPlacementGroupName -Location $location -Tag @{key1 = 'val1'} | Format-List

ResourceGroupName                       : $resourceGroupName
ProximityPlacementGroupType             : Standard
VirtualMachinesColocationStatus         : {}
VirtualMachineScaleSetsColocationStatus : {}
AvailabilitySetsColocationStatus        : {}
ColocationStatus                        :
Id                                      : /subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/resourceGroups/$resourceGroupName/providers/Microsoft.Compute/proximityPlacementGroups/$proximityPlacementGroupName
Name                                    : $proximityPlacementGroupName
Type                                    : Microsoft.Compute/proximityPlacementGroups
Location                                : $location
Tags                                    : {[key1, val1]}
VirtualMachines                         : {}
VirtualMachineScaleSets                 : {}
AvailabilitySets                        : {}
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> New-AzProximityPlacementGroup -ResourceGroupName $resourceGroupName -Name $proximityPlacementGroupName -Location $location -Tag @{key1 = 'val1'} | Format-List

ResourceGroupName                       : $resourceGroupName
ProximityPlacementGroupType             : StandardColocationStatus                        :
Id                                      : /subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/resourceGroups/$resourceGroupName/providers/Microsoft.Compute/proximityPlacementGroups/$proximityPlacementGroupName
Name                                    : $proximityPlacementGroupName
Type                                    : Microsoft.Compute/proximityPlacementGroups
Location                                : $location
Tags                                    : {[key1, val1]}
VirtualMachines                         : {}
VirtualMachineScaleSets                 : {}
AvailabilitySets                        : {}
```

### `Remove-AzProximityPlacementGroup`

- Tipe generik untuk properti `VirtualMachines` , , dan telah diubah dari menjadi `VirtualMachineScaleSets` `AvailabilitySets` `System.Collections.Generic.IList1[Microsoft.Azure.Management.Compute.Models.SubResource]` `System.Collections.Generic.IList1[Microsoft.Azure.Management.Compute.Models.SubResourceWithColocationStatus]` .
- Properti `VirtualMachinesColocationStatus` , `VirtualMachineScaleSetsColocationStatus` , dan dari tipe `AvailabilitySetsColocationStatus` telah `Microsoft.Azure.Commands.Compute.Automation.Models.PSProximityPlacementGroup` dihapus.

#### <a name="before"></a>Sebelum

```powershell
PS C:\> Get-AzProximityPlacementGroup -ResourceGroupName $resourceGroupName -Name $proximityPlacementGroupName | Remove-AzProximityPlacementGroup | Format-List

ResourceGroupName                       : $resourceGroupName
ProximityPlacementGroupType             : Standard
VirtualMachinesColocationStatus         : {}
VirtualMachineScaleSetsColocationStatus : {}
AvailabilitySetsColocationStatus        : {}
ColocationStatus                        :
Id                                      : /subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/resourceGroups/$resourceGroupName/providers/Microsoft.Compute/proximityPlacementGroups/$proximityPlacementGroupName
Name                                    : $proximityPlacementGroupName
Type                                    : Microsoft.Compute/proximityPlacementGroups
Location                                : $location
Tags                                    : {[key1, val1]}
VirtualMachines                         : {}
VirtualMachineScaleSets                 : {}
AvailabilitySets                        : {}
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> Get-AzProximityPlacementGroup -ResourceGroupName $resourceGroupName -Name $proximityPlacementGroupName | Remove-AzProximityPlacementGroup | Format-List

ResourceGroupName                       : $resourceGroupName
ProximityPlacementGroupType             : StandardColocationStatus                        :
Id                                      : /subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/resourceGroups/$resourceGroupName/providers/Microsoft.Compute/proximityPlacementGroups/$proximityPlacementGroupName
Name                                    : $proximityPlacementGroupName
Type                                    : Microsoft.Compute/proximityPlacementGroups
Location                                : $location
Tags                                    : {[key1, val1]}
VirtualMachines                         : {}
VirtualMachineScaleSets                 : {}
AvailabilitySets                        : {}
```

### `Get-AzProximityPlacementGroup`

- Tipe generik untuk properti `VirtualMachines` , , dan telah diubah dari menjadi `VirtualMachineScaleSets` `AvailabilitySets` `System.Collections.Generic.IList1[Microsoft.Azure.Management.Compute.Models.SubResource]` `System.Collections.Generic.IList1[Microsoft.Azure.Management.Compute.Models.SubResourceWithColocationStatus]` .
- Properti `VirtualMachinesColocationStatus` , `VirtualMachineScaleSetsColocationStatus` , dan dari tipe `AvailabilitySetsColocationStatus` telah `Microsoft.Azure.Commands.Compute.Automation.Models.PSProximityPlacementGroup` dihapus.

#### <a name="before"></a>Sebelum

```powershell
PS C:\> Get-AzProximityPlacementGroup -ResourceGroupName $resourceGroupName -Name $proximityPlacementGroupName | Format-List

ResourceGroupName                       : $resourceGroupName
ProximityPlacementGroupType             : Standard
VirtualMachinesColocationStatus         : {}
VirtualMachineScaleSetsColocationStatus : {}
AvailabilitySetsColocationStatus        : {}
ColocationStatus                        :
Id                                      : /subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/resourceGroups/$resourceGroupName/providers/Microsoft.Compute/proximityPlacementGroups/$proximityPlacementGroupName
Name                                    : $proximityPlacementGroupName
Type                                    : Microsoft.Compute/proximityPlacementGroups
Location                                : $location
Tags                                    : {[key1, val1]}
VirtualMachines                         : {}
VirtualMachineScaleSets                 : {}
AvailabilitySets                        : {}
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> Get-AzProximityPlacementGroup -ResourceGroupName $resourceGroupName -Name $proximityPlacementGroupName | Format-List

ResourceGroupName                       : $resourceGroupName
ProximityPlacementGroupType             : StandardColocationStatus                        :
Id                                      : /subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/resourceGroups/$resourceGroupName/providers/Microsoft.Compute/proximityPlacementGroups/$proximityPlacementGroupName
Name                                    : $proximityPlacementGroupName
Type                                    : Microsoft.Compute/proximityPlacementGroups
Location                                : $location
Tags                                    : {[key1, val1]}
VirtualMachines                         : {}
VirtualMachineScaleSets                 : {}
AvailabilitySets                        : {}
```

### `Add-AzVmssAdditionalUnattendContent`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Add-AzVmssDataDisk`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Add-AzVmssExtension`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Add-AzVmssNetworkInterfaceConfiguration`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Add-AzVmssSecret`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Add-AzVmssSshPublicKey`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Add-AzVmssWinRMListener`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `New-AzVmssConfig`

- Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .
- Tidak lagi mendukung parameter `AutomaticRepairMaxInstanceRepairsPercent` dan tidak ada alias yang ditemukan untuk nama parameter asli.
- Tidak lagi mendukung parameter `AssignIdentity` dan tidak ada alias yang ditemukan untuk nama parameter asli.
- Kumpulan parameter `__AllParameterSets` telah dihapus.
- Kumpulan parameter `ExplicitIdentityParameterSet` telah dihapus.
- Kumpulan parameter `AssignIdentityParameterSet` telah dihapus.

### `Remove-AzVmssDataDisk`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Remove-AzVmssExtension`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Remove-AzVmssNetworkInterfaceConfiguration`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Set-AzVmssBootDiagnostic`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Set-AzVmssOsProfile`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Set-AzVmssRollingUpgradePolicy`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Set-AzVmssStorageProfile`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `New-AzVmss`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Repair-AzVmssServiceFabricUpdateDomain`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Get-AzVmss`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Set-AzVmssOrchestrationServiceState`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Update-AzVmss`

- Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .
- Tidak lagi mendukung parameter `AutomaticRepairMaxInstanceRepairsPercent` dan tidak ada alias yang ditemukan untuk nama parameter asli.
- Kumpulan parameter `__AllParameterSets` telah dihapus.
- Kumpulan parameter `ExplicitIdentityParameterSet` telah dihapus.

### `Add-AzVmssDiagnosticsExtension`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

### `Disable-AzVmssDiskEncryption`

Tipe properti tipe `AutomaticRepairsPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy` .

## <a name="azkeyvault"></a>Az.KeyVault

### `New-AzKeyVaultCertificateOrganizationDetail`

Alias `New-AzKeyVaultCertificateOrganizationDetails` dihapus. Silakan gunakan `New-AzKeyVaultCertificateOrganizationDetail` .

#### <a name="before"></a>Sebelum

```powershell
PS C:\> New-AzKeyVaultCertificateOrganizationDetails -AdministratorDetails $AdminDetails
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> New-AzKeyVaultCertificateOrganizationDetail -AdministratorDetails $AdminDetails
```

### `New-AzKeyVaultCertificateAdministratorDetail`

Alias `New-AzKeyVaultCertificateAdministratorDetails` dihapus. Silakan gunakan `New-AzKeyVaultCertificateAdministratorDetail` .

#### <a name="before"></a>Sebelum

```powershell
PS C:\> $AdminDetails = New-AzKeyVaultCertificateAdministratorDetails -FirstName 'Patti' -LastName 'Fuller' -EmailAddress 'patti.fuller@contoso.com' -PhoneNumber '5553334444'
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> $AdminDetails = New-AzKeyVaultCertificateAdministratorDetail -FirstName 'Patti' -LastName 'Fuller' -EmailAddress 'patti.fuller@contoso.com' -PhoneNumber '5553334444'
```

### `New-AzKeyVault`

`-EnableSoftDelete` dihapus, karena penghapusan sementara diaktifkan secara default. Silakan gunakan `-DisableSoftDelete` jika Anda tidak menginginkan perilaku ini.

#### <a name="before"></a>Sebelum

```powershell
PS C:\> New-AzKeyVault -VaultName 'Contoso03Vault' -ResourceGroupName 'Group14' -Location 'East US' -EnableSoftDelete
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> New-AzKeyVault -VaultName 'Contoso03Vault' -ResourceGroupName 'Group14' -Location 'East US'
```

## <a name="azmonitor"></a>Az.Monitor

### `Add-AzLogProfile`

Tipe properti tipe `RetentionPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Insights.OutputClasses.PSLogProfile` `Microsoft.Azure.Management.Monitor.Management.Models.RetentionPolicy` `Microsoft.Azure.Management.Monitor.Models.RetentionPolicy` .

### `Get-AzLogProfile`

Tipe properti tipe `RetentionPolicy` telah berubah dari menjadi `Microsoft.Azure.Commands.Insights.OutputClasses.PSLogProfile` `Microsoft.Azure.Management.Monitor.Management.Models.RetentionPolicy` `Microsoft.Azure.Management.Monitor.Models.RetentionPolicy` .

### `New-AzMetricAlertRuleV2Criteria`

Kumpulan parameter `__AllParameterSets` untuk cmdlet telah `New-AzMetricAlertRuleV2Criteria` dihapus.

## <a name="aznetwork"></a>Az.Network

### `Get-AzNetworkWatcherConnectionMonitor`

Tipe generik untuk properti `RoundTripTimeMs` telah diubah dari menjadi `System.Nullable1[System.Int32]` `System.Nullable1[System.Double]` .

### `New-AzNetworkWatcherConnectionMonitorTestConfigurationObject`

Tipe umum untuk parameter `SuccessThresholdRoundTripTimeMs` telah diubah dari menjadi `System.Nullable1[System.Int32]` `System.Nullable1[System.Double]` .

## <a name="azoperationalinsights"></a>Az.OperationalInsights

### `Get-AzOperationalInsightsDataSource`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsApplicationInsightsDataSource`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsAzureActivityLogDataSource`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsCustomLogDataSource`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsLinuxPerformanceObjectDataSource`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsLinuxSyslogDataSource`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsWindowsEventDataSource`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsWindowsPerformanceCounterDataSource`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Remove-AzOperationalInsightsDataSource`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Disable-AzOperationalInsightsIISLogCollection`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Disable-AzOperationalInsightsLinuxCustomLogCollection`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Disable-AzOperationalInsightsLinuxPerformanceCollection`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Disable-AzOperationalInsightsLinuxSyslogCollection`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Enable-AzOperationalInsightsIISLogCollection`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Enable-AzOperationalInsightsLinuxCustomLogCollection`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Enable-AzOperationalInsightsLinuxPerformanceCollection`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Enable-AzOperationalInsightsLinuxSyslogCollection`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Get-AzOperationalInsightsSavedSearch`

Properti `Metadata` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSSearchListSavedSearchResponse` telah dihapus.

### `Get-AzOperationalInsightsSavedSearchResult`

Cmdlet `Get-AzOperationalInsightsSavedSearchResult` tidak lagi didukung oleh SDK dan telah dihapus.

### `Get-AzOperationalInsightsSearchResult`

Cmdlet `Get-AzOperationalInsightsSearchResult` tidak lagi didukung oleh SDK dan telah dihapus.

### `Get-AzOperationalInsightsStorageInsight`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsStorageInsight`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Remove-AzOperationalInsightsStorageInsight`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Set-AzOperationalInsightsStorageInsight`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Get-AzOperationalInsightsLinkTarget`

Cmdlet `Get-AzOperationalInsightsLinkTarget` tidak lagi didukung oleh SDK dan telah dihapus.

### `Get-AzOperationalInsightsWorkspace`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsWorkspace`

- Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.
- Cmdlet `New-AzOperationalInsightsWorkspace` tidak lagi mendukung parameter dan `CustomerId` tidak ada alias yang ditemukan untuk nama parameter aslinya.
- Kumpulan parameter `__AllParameterSets` untuk cmdlet telah `New-AzOperationalInsightsWorkspace` dihapus.

### `Set-AzOperationalInsightsWorkspace`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Invoke-AzOperationalInsightsQuery`

Properti `PortalUrl` tipe `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

## <a name="azresources"></a>Az.Resources

### `Get-AzDeploymentScript`

Tipe properti tipe `Status` telah berubah dari menjadi `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsDeploymentScript` `Microsoft.Azure.Management.ResourceManager.Models.ScriptStatus` `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsScriptStatus` .

### `Get-AzDeploymentScriptLog`

Tipe properti tipe `Status` telah berubah dari menjadi `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsDeploymentScript` `Microsoft.Azure.Management.ResourceManager.Models.ScriptStatus` `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsScriptStatus` .

### `Save-AzDeploymentScriptLog`

Tipe properti tipe `Status` telah berubah dari menjadi `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsDeploymentScript` `Microsoft.Azure.Management.ResourceManager.Models.ScriptStatus` `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsScriptStatus` .

### `Get-AzResourceLock, New-AzResourceLock, Remove-AzResourceLock, Set-AzResourceLock`

Parameter `TenantLevel` telah dihapus.

### `Get-AzPolicyAlias`

Tipe generik untuk properti `Aliases` telah diubah dari menjadi `System.Collections.Generic.IList1[Microsoft.Azure.Management.ResourceManager.Models.AliasType]` `System.Collections.Generic.IList1[Microsoft.Azure.Management.ResourceManager.Models.Alias]` .

### `New-AzPolicyAssignment`

- Cmdlet `New-AzPolicyAssignment` tidak lagi mendukung tipe `System.Management.Automation.PSObject` untuk `PolicyDefinition` parameter.
- Cmdlet `New-AzPolicyAssignment` tidak lagi mendukung tipe `System.Management.Automation.PSObject` untuk `PolicySetDefinition` parameter.

### `Remove-AzDeploymentScript`

Tipe properti tipe `Status` telah berubah dari menjadi `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsDeploymentScript` `Microsoft.Azure.Management.ResourceManager.Models.ScriptStatus` `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsScriptStatus` .

## <a name="azstorage"></a>Az.Storage

### <a name="update-azstorageaccountnetworkruleset-get-azstorageaccountnetworkruleset"></a>`Update-AzStorageAccountNetworkRuleSet`, `Get-AzStorageAccountNetworkRuleSet`

Changed NetWorkRule DefaultAction value from: Allow = 1, Deny = 0, to: Allow = 0, Deny = 1.

### <a name="new-azstoragetable-get-azstoragetable"></a>`New-AzStorageTable`, `Get-AzStorageTable`

Objek output AzureStorageTable.CloudTable.ServiceClient telah menghapus 2 properti: ConnectionPolicy, ConsistencyLevel.

### <a name="get-azstoragefile-remove-azstoragefile-get-azstoragefilecontent-set-azstoragefilecontent-start-azstoragefilecopy"></a>`Get-AzStorageFile`, `Remove-AzStorageFile`, `Get-AzStorageFileContent`, `Set-AzStorageFileContent`, `Start-AzStorageFileCopy`

Mengubah tipe output dari CloudFile ke AzureStorageFile, output asli akan menjadi properti anak "CloudFile" dari output baru

#### <a name="before"></a>Sebelum

```powershell
PS C:\> $file = Get-AzStorageFile -ShareName $shareName -Path testfile -Context $ctx

PS C:\> Remove-AzStorageFile -File $file
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> $file = Get-AzStorageFile -ShareName $shareName -Path testfile -Context $ctx

PS C:\> Remove-AzStorageFile -File $file.CloudFile
```

### <a name="get-azstoragefile-new-azstoragedirectory-remove-azstoragedirectory"></a>`Get-AzStorageFile`, `New-AzStorageDirectory`, `Remove-AzStorageDirectory`

Ubah tipe output dari CloudFileDirectory ke AzureStorageFileDirectory, output asli akan menjadi properti anak "CloudFileDirectory" dari output baru

#### <a name="before"></a>Sebelum

```powershell
PS C:\> $dir = Get-AzStorageFile -ShareName $shareName -Path testdir -Context $ctx

PS C:\> Remove-AzStorageDirectory -Directory $dir
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> $dir = Get-AzStorageFile -ShareName $shareName -Path testdir -Context $ctx

PS C:\> Remove-AzStorageDirectory -Directory $dir.CloudFileDirectory
```

### <a name="get-azstorageshare-new-azstorageshare-remove-azstorageshare"></a>`Get-AzStorageShare`, `New-AzStorageShare`, `Remove-AzStorageShare`

Ubah tipe output dari FileShareProperties ke AzureStorageFileShare, output asli akan menjadi properti anak "CloudFileShare" dari output baru

#### <a name="before"></a>Sebelum

```powershell
PS C:\> $share = Get-AzStorageShare -Name $shareName -Context $ctx

PS C:\> Remove-AzStorageShare -Share $share
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> $share = Get-AzStorageShare -Name $shareName -Context $ctx

PS C:\> Remove-AzStorageShare -Share $share.CloudFileShare
```

### `Set-AzStorageShareQuota`

Change output type from FileShareProperties to AzureStorageFileShare, the original output will become sub child property ""CloudFileShare.Properties"" of the new output

#### <a name="before"></a>Sebelum

```powershell
PS C:\> $shareProperties = Set-AzStorageShareQuota -Name $shareName -Quota 100 -Context $ctx

PS C:\> $shareProperties

ETag                LastModified                Quota
----                ------------                -----
"0x8D7F5BC7789FC63" 5/11/2020 3:03:30 PM +00:00   100
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> $share = Set-AzStorageShareQuota -Name $shareName -Quota 100 -Context $ctx

PS C:\> $share

   File End Point: https://weiors1.file.core.windows.net/

Name     QuotaGiB LastModified                IsSnapshot SnapshotTime
----     -------- ------------                ---------- ------------
weitest1 100      5/11/2020 3:03:30 PM +00:00 False

PS C:\> $share.CloudFileShare.Properties

ETag                LastModified                Quota
----                ------------                -----
"0x8D7F5BC7789FC63" 5/11/2020 3:03:30 PM +00:00   100
```

### `Remove-AzStorageDirectory`

Saat menghapus sub Direktori File dengan objek Direktori induk dan -Jalur, Tidak bisa menginput -Jalur dari saluran dengan tipe (string) cocok lagi.

#### <a name="before"></a>Sebelum

```powershell
PS C:\> $dir = Get-AzStorageFile -ShareName $shareName -Path testdir -Context $ctx

PS C:\> @('dir1', 'dir2') | Remove-AzStorageDirectory -Directory $dir
```

#### <a name="after"></a>Setelah

```powershell
PS C:\> $dir = Get-AzStorageFile -ShareName $shareName -Path testdir -Context $ctx

PS C:\> $paths = @(
    [PSCustomObject]@{  Path = 'dir1 }
    [PSCustomObject]@{ Path = 'dir2' }
)

PS C:\> $paths | Remove-AzStorageDirectory -Directory $dir.CloudFileDirectory
```
