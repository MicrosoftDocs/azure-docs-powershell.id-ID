---
description: Panduan migrasi ini berisi daftar perubahan yang melanggar yang dibuat untuk Azure PowerShell dalam rilis Az versi 4.1.0.
ms.custom: devx-track-azurepowershell
ms.date: 04/26/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Panduan Migrasi untuk Az 4.1.0
ms.openlocfilehash: 1a35a57fda07f35d9ac8f8725549b5fd660b219f
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144595418"
---
# <a name="migration-guide-for-az-410"></a>Panduan Migrasi untuk Az 4.1.0

Dokumen ini menjelaskan perubahan antara Az versi 3.0.0 dan 4.1.0.

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

Jenis properti `Type` dari jenis `Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementServiceIdentity` berubah dari `Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementServiceIdentityType` menjadi `System.String`.

### `New-AzApiManagement`

- Cmdlet `New-AzApiManagement` tidak lagi mendukung parameter `AssignIdentity` dan tidak ada alias yang ditemukan untuk nama parameter asli.
- Set parameter `__AllParameterSets` untuk cmdlet `New-AzApiManagement` telah dihapus.

### `Set-AzApiManagement`

- Cmdlet `Set-AzApiManagement` tidak lagi mendukung parameter `AssignIdentity` dan tidak ada alias yang ditemukan untuk nama parameter asli.
- Set parameter `__AllParameterSets` untuk cmdlet `Set-AzApiManagement` telah dihapus.

### `Get-AzApiManagementProperty`

Cmdlet `Get-AzApiManagementProperty` telah diganti dengan `Get-AzApiManagementNamedValue`.

### `New-AzApiManagementProperty`

Cmdlet `New-AzApiManagementProperty` telah diganti dengan `New-AzApiManagementNamedValue`.

### `Remove-AzApiManagementProperty`

Cmdlet `Remove-AzApiManagementProperty` telah diganti dengan `Remove-AzApiManagementNamedValue`.

### `Set-AzApiManagementProperty`

Cmdlet `Set-AzApiManagementProperty` telah diganti dengan `Set-AzApiManagementNamedValue`.

## <a name="azbatch"></a>Az.Batch

### <a name="get-azbatchapplication-new-azbatchapplication"></a>`Get-AzBatchApplication`, `New-AzBatchApplication`

Properti `ApplicationPackages` jenis `Microsoft.Azure.Commands.Batch.Models.PSApplication` telah dihapus.

### <a name="get-azbatchcomputenode-new-azbatchpool"></a>`Get-AzBatchComputeNode`, `New-AzBatchPool`

Properti `PublicIPs` jenis `Microsoft.Azure.Commands.Batch.Models.PSNetworkConfiguration` telah dihapus

### <a name="get-azbatchapplicationpackage-new-azbatchapplicationpackage"></a>`Get-AzBatchApplicationPackage`, `New-AzBatchApplicationPackage`

Jenis properti `StorageUrlExpiry` dari jenis `Microsoft.Azure.Commands.Batch.Models.PSApplicationPackage` berubah dari `System.DateTime` menjadi `System.DateTime?`.

## <a name="azcompute"></a>Az.Compute

### `Remove-AzVmssDiagnosticsExtension`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Get-AzVMImage`

- Cmdlet `Get-AzVMImage` tidak lagi mendukung parameter `FilterExpression` dan tidak ada alias yang ditemukan untuk nama parameter asli.
- Set parameter `ListVMImage` untuk cmdlet `Get-AzVMImage` telah dihapus.

### `New-AzVMConfig`

- Cmdlet `New-AzVMConfig` tidak lagi mendukung parameter `AssignIdentity` dan tidak ada alias yang ditemukan untuk nama parameter asli.
- Set parameter `AssignIdentityParameterSet` untuk cmdlet `New-AzVMConfig` telah dihapus.

### `Update-AzVM`

- Cmdlet `Update-AzVM` tidak lagi mendukung parameter `AssignIdentity` dan tidak ada alias yang ditemukan untuk nama parameter asli.
- Set parameter `AssignIdentityParameterSet` untuk cmdlet `Update-AzVM` telah dihapus.

### `New-AzProximityPlacementGroup`

- Jenis generik untuk properti`VirtualMachines`, `VirtualMachineScaleSets`, dan `AvailabilitySets` telah berubah dari `System.Collections.Generic.IList1[Microsoft.Azure.Management.Compute.Models.SubResource]` menjadi `System.Collections.Generic.IList1[Microsoft.Azure.Management.Compute.Models.SubResourceWithColocationStatus]`.
- Properti `VirtualMachinesColocationStatus`, `VirtualMachineScaleSetsColocationStatus`, dan `AvailabilitySetsColocationStatus` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSProximityPlacementGroup` telah dihapus.

#### <a name="before"></a>Sebelumnya

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

#### <a name="after"></a>Sesudahnya

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

- Jenis generik untuk properti`VirtualMachines`, `VirtualMachineScaleSets`, dan `AvailabilitySets` telah berubah dari `System.Collections.Generic.IList1[Microsoft.Azure.Management.Compute.Models.SubResource]` menjadi `System.Collections.Generic.IList1[Microsoft.Azure.Management.Compute.Models.SubResourceWithColocationStatus]`.
- Properti `VirtualMachinesColocationStatus`, `VirtualMachineScaleSetsColocationStatus`, dan `AvailabilitySetsColocationStatus` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSProximityPlacementGroup` telah dihapus.

#### <a name="before"></a>Sebelumnya

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

#### <a name="after"></a>Sesudahnya

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

- Jenis generik untuk properti`VirtualMachines`, `VirtualMachineScaleSets`, dan `AvailabilitySets` telah berubah dari `System.Collections.Generic.IList1[Microsoft.Azure.Management.Compute.Models.SubResource]` menjadi `System.Collections.Generic.IList1[Microsoft.Azure.Management.Compute.Models.SubResourceWithColocationStatus]`.
- Properti `VirtualMachinesColocationStatus`, `VirtualMachineScaleSetsColocationStatus`, dan `AvailabilitySetsColocationStatus` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSProximityPlacementGroup` telah dihapus.

#### <a name="before"></a>Sebelumnya

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

#### <a name="after"></a>Sesudahnya

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

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Add-AzVmssDataDisk`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Add-AzVmssExtension`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Add-AzVmssNetworkInterfaceConfiguration`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Add-AzVmssSecret`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Add-AzVmssSshPublicKey`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Add-AzVmssWinRMListener`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `New-AzVmssConfig`

- Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.
- Tidak lagi mendukung parameter `AutomaticRepairMaxInstanceRepairsPercent` dan tidak ada alias yang ditemukan untuk nama parameter asli.
- Tidak lagi mendukung parameter `AssignIdentity` dan tidak ada alias yang ditemukan untuk nama parameter asli.
- Set parameter `__AllParameterSets` telah dihapus.
- Set parameter `ExplicitIdentityParameterSet` telah dihapus.
- Set parameter `AssignIdentityParameterSet` telah dihapus.

### `Remove-AzVmssDataDisk`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Remove-AzVmssExtension`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Remove-AzVmssNetworkInterfaceConfiguration`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Set-AzVmssBootDiagnostic`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Set-AzVmssOsProfile`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Set-AzVmssRollingUpgradePolicy`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Set-AzVmssStorageProfile`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `New-AzVmss`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Repair-AzVmssServiceFabricUpdateDomain`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Get-AzVmss`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Set-AzVmssOrchestrationServiceState`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Update-AzVmss`

- Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.
- Tidak lagi mendukung parameter `AutomaticRepairMaxInstanceRepairsPercent` dan tidak ada alias yang ditemukan untuk nama parameter asli.
- Set parameter `__AllParameterSets` telah dihapus.
- Set parameter `ExplicitIdentityParameterSet` telah dihapus.

### `Add-AzVmssDiagnosticsExtension`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

### `Disable-AzVmssDiskEncryption`

Jenis properti `AutomaticRepairsPolicy` dari jenis `Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet` berubah dari `Microsoft.Azure.Commands.Compute.Automation.Models.PSAutomaticRepairsPolicy` menjadi `Microsoft.Azure.Management.Compute.Models.AutomaticRepairsPolicy`.

## <a name="azkeyvault"></a>Az.KeyVault

### `New-AzKeyVaultCertificateOrganizationDetail`

Alias `New-AzKeyVaultCertificateOrganizationDetails` dihapus. Harap gunakan `New-AzKeyVaultCertificateOrganizationDetail`.

#### <a name="before"></a>Sebelumnya

```powershell
PS C:\> New-AzKeyVaultCertificateOrganizationDetails -AdministratorDetails $AdminDetails
```

#### <a name="after"></a>Sesudahnya

```powershell
PS C:\> New-AzKeyVaultCertificateOrganizationDetail -AdministratorDetails $AdminDetails
```

### `New-AzKeyVaultCertificateAdministratorDetail`

Alias `New-AzKeyVaultCertificateAdministratorDetails` dihapus. Harap gunakan `New-AzKeyVaultCertificateAdministratorDetail`.

#### <a name="before"></a>Sebelumnya

```powershell
PS C:\> $AdminDetails = New-AzKeyVaultCertificateAdministratorDetails -FirstName 'Patti' -LastName 'Fuller' -EmailAddress 'patti.fuller@contoso.com' -PhoneNumber '5553334444'
```

#### <a name="after"></a>Sesudahnya

```powershell
PS C:\> $AdminDetails = New-AzKeyVaultCertificateAdministratorDetail -FirstName 'Patti' -LastName 'Fuller' -EmailAddress 'patti.fuller@contoso.com' -PhoneNumber '5553334444'
```

### `New-AzKeyVault`

`-EnableSoftDelete` dihapus, karena penghapusan sementara diaktifkan secara default. Silakan gunakan `-DisableSoftDelete` jika Anda tidak menginginkan perilaku ini.

#### <a name="before"></a>Sebelumnya

```powershell
PS C:\> New-AzKeyVault -VaultName 'Contoso03Vault' -ResourceGroupName 'Group14' -Location 'East US' -EnableSoftDelete
```

#### <a name="after"></a>Sesudahnya

```powershell
PS C:\> New-AzKeyVault -VaultName 'Contoso03Vault' -ResourceGroupName 'Group14' -Location 'East US'
```

## <a name="azmonitor"></a>Az.Monitor

### `Add-AzLogProfile`

Jenis properti `RetentionPolicy` dari jenis `Microsoft.Azure.Commands.Insights.OutputClasses.PSLogProfile` berubah dari `Microsoft.Azure.Management.Monitor.Management.Models.RetentionPolicy` menjadi `Microsoft.Azure.Management.Monitor.Models.RetentionPolicy`.

### `Get-AzLogProfile`

Jenis properti `RetentionPolicy` dari jenis `Microsoft.Azure.Commands.Insights.OutputClasses.PSLogProfile` berubah dari `Microsoft.Azure.Management.Monitor.Management.Models.RetentionPolicy` menjadi `Microsoft.Azure.Management.Monitor.Models.RetentionPolicy`.

### `New-AzMetricAlertRuleV2Criteria`

Set parameter `__AllParameterSets` untuk cmdlet `New-AzMetricAlertRuleV2Criteria` telah dihapus.

## <a name="aznetwork"></a>Az.Network

### `Get-AzNetworkWatcherConnectionMonitor`

Jenis generik untuk properti `RoundTripTimeMs` telah berubah dari `System.Nullable1[System.Int32]`menjadi `System.Nullable1[System.Double]`.

### `New-AzNetworkWatcherConnectionMonitorTestConfigurationObject`

Jenis generik untuk parameter `SuccessThresholdRoundTripTimeMs` telah berubah dari `System.Nullable1[System.Int32]`menjadi `System.Nullable1[System.Double]`.

## <a name="azoperationalinsights"></a>Az.OperationalInsights

### `Get-AzOperationalInsightsDataSource`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsApplicationInsightsDataSource`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsAzureActivityLogDataSource`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsCustomLogDataSource`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsLinuxPerformanceObjectDataSource`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsLinuxSyslogDataSource`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsWindowsEventDataSource`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsWindowsPerformanceCounterDataSource`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Remove-AzOperationalInsightsDataSource`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Disable-AzOperationalInsightsIISLogCollection`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Disable-AzOperationalInsightsLinuxCustomLogCollection`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Disable-AzOperationalInsightsLinuxPerformanceCollection`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Disable-AzOperationalInsightsLinuxSyslogCollection`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Enable-AzOperationalInsightsIISLogCollection`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Enable-AzOperationalInsightsLinuxCustomLogCollection`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Enable-AzOperationalInsightsLinuxPerformanceCollection`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Enable-AzOperationalInsightsLinuxSyslogCollection`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Get-AzOperationalInsightsSavedSearch`

Properti `Metadata` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSSearchListSavedSearchResponse` telah dihapus.

### `Get-AzOperationalInsightsSavedSearchResult`

Cmdlet `Get-AzOperationalInsightsSavedSearchResult` tidak didukung oleh SDK lagi dan telah dihapus.

### `Get-AzOperationalInsightsSearchResult`

Cmdlet `Get-AzOperationalInsightsSearchResult` tidak didukung oleh SDK lagi dan telah dihapus.

### `Get-AzOperationalInsightsStorageInsight`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsStorageInsight`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Remove-AzOperationalInsightsStorageInsight`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Set-AzOperationalInsightsStorageInsight`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Get-AzOperationalInsightsLinkTarget`

Cmdlet `Get-AzOperationalInsightsLinkTarget` tidak didukung oleh SDK lagi dan telah dihapus.

### `Get-AzOperationalInsightsWorkspace`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `New-AzOperationalInsightsWorkspace`

- Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.
- Cmdlet `New-AzOperationalInsightsWorkspace` tidak lagi mendukung parameter `CustomerId` dan tidak ada alias yang ditemukan untuk nama parameter asli.
- Set parameter `__AllParameterSets` untuk cmdlet `New-AzOperationalInsightsWorkspace` telah dihapus.

### `Set-AzOperationalInsightsWorkspace`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

### `Invoke-AzOperationalInsightsQuery`

Properti `PortalUrl` jenis `Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace` telah dihapus.

## <a name="azresources"></a>Az.Resources

### `Get-AzDeploymentScript`

Jenis properti `Status` dari jenis `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsDeploymentScript` berubah dari `Microsoft.Azure.Management.ResourceManager.Models.ScriptStatus` menjadi `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsScriptStatus`.

### `Get-AzDeploymentScriptLog`

Jenis properti `Status` dari jenis `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsDeploymentScript` berubah dari `Microsoft.Azure.Management.ResourceManager.Models.ScriptStatus` menjadi `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsScriptStatus`.

### `Save-AzDeploymentScriptLog`

Jenis properti `Status` dari jenis `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsDeploymentScript` berubah dari `Microsoft.Azure.Management.ResourceManager.Models.ScriptStatus` menjadi `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsScriptStatus`.

### `Get-AzResourceLock, New-AzResourceLock, Remove-AzResourceLock, Set-AzResourceLock`

Parameter `TenantLevel` telah dihapus.

### `Get-AzPolicyAlias`

Jenis generik untuk properti `Aliases` telah berubah dari `System.Collections.Generic.IList1[Microsoft.Azure.Management.ResourceManager.Models.AliasType]`menjadi `System.Collections.Generic.IList1[Microsoft.Azure.Management.ResourceManager.Models.Alias]`.

### `New-AzPolicyAssignment`

- Cmdlet `New-AzPolicyAssignment` tidak lagi mendukung jenis `System.Management.Automation.PSObject` untuk parameter `PolicyDefinition`.
- Cmdlet `New-AzPolicyAssignment` tidak lagi mendukung jenis `System.Management.Automation.PSObject` untuk parameter `PolicySetDefinition`.

### `Remove-AzDeploymentScript`

Jenis properti `Status` dari jenis `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsDeploymentScript` berubah dari `Microsoft.Azure.Management.ResourceManager.Models.ScriptStatus` menjadi `Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PsScriptStatus`.

## <a name="azstorage"></a>Az.Storage

### <a name="update-azstorageaccountnetworkruleset-get-azstorageaccountnetworkruleset"></a>`Update-AzStorageAccountNetworkRuleSet`, `Get-AzStorageAccountNetworkRuleSet`

Mengubah nilai NetWorkRule DefaultAction dari: Izinkan = 1, Tolak = 0, ke: Izinkan = 0, Tolak = 1.

### <a name="new-azstoragetable-get-azstoragetable"></a>`New-AzStorageTable`, `Get-AzStorageTable`

Objek output AzureStorageTable.CloudTable.ServiceClient memiliki 2 properti yang dihapus: ConnectionPolicy, ConsistencyLevel.

### <a name="get-azstoragefile-remove-azstoragefile-get-azstoragefilecontent-set-azstoragefilecontent-start-azstoragefilecopy"></a>`Get-AzStorageFile`, `Remove-AzStorageFile`, `Get-AzStorageFileContent`, `Set-AzStorageFileContent`, `Start-AzStorageFileCopy`

Mengubah jenis output dari CloudFile ke AzureStorageFile, output asli akan menjadi properti turunan “CloudFile” dari output baru

#### <a name="before"></a>Sebelumnya

```powershell
PS C:\> $file = Get-AzStorageFile -ShareName $shareName -Path testfile -Context $ctx

PS C:\> Remove-AzStorageFile -File $file
```

#### <a name="after"></a>Sesudahnya

```powershell
PS C:\> $file = Get-AzStorageFile -ShareName $shareName -Path testfile -Context $ctx

PS C:\> Remove-AzStorageFile -File $file.CloudFile
```

### <a name="get-azstoragefile-new-azstoragedirectory-remove-azstoragedirectory"></a>`Get-AzStorageFile`, `New-AzStorageDirectory`, `Remove-AzStorageDirectory`

Mengubah jenis output dari CloudFileDirectory ke AzureStorageFileDirectory, output asli akan menjadi properti turunan “CloudFileDirectory” dari output baru

#### <a name="before"></a>Sebelumnya

```powershell
PS C:\> $dir = Get-AzStorageFile -ShareName $shareName -Path testdir -Context $ctx

PS C:\> Remove-AzStorageDirectory -Directory $dir
```

#### <a name="after"></a>Sesudahnya

```powershell
PS C:\> $dir = Get-AzStorageFile -ShareName $shareName -Path testdir -Context $ctx

PS C:\> Remove-AzStorageDirectory -Directory $dir.CloudFileDirectory
```

### <a name="get-azstorageshare-new-azstorageshare-remove-azstorageshare"></a>`Get-AzStorageShare`, `New-AzStorageShare`, `Remove-AzStorageShare`

Mengubah jenis output dari FileShareProperties ke AzureStorageFileShare, output asli akan menjadi properti turunan “CloudFileShare” dari output baru

#### <a name="before"></a>Sebelumnya

```powershell
PS C:\> $share = Get-AzStorageShare -Name $shareName -Context $ctx

PS C:\> Remove-AzStorageShare -Share $share
```

#### <a name="after"></a>Sesudahnya

```powershell
PS C:\> $share = Get-AzStorageShare -Name $shareName -Context $ctx

PS C:\> Remove-AzStorageShare -Share $share.CloudFileShare
```

### `Set-AzStorageShareQuota`

Mengubah jenis output dari FileShareProperties ke AzureStorageFileShare, output asli akan menjadi properti sub-turunan “”CloudFileShare.Properties”” dari output baru

#### <a name="before"></a>Sebelumnya

```powershell
PS C:\> $shareProperties = Set-AzStorageShareQuota -Name $shareName -Quota 100 -Context $ctx

PS C:\> $shareProperties

ETag                LastModified                Quota
----                ------------                -----
"0x8D7F5BC7789FC63" 5/11/2020 3:03:30 PM +00:00   100
```

#### <a name="after"></a>Sesudahnya

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

Saat menghapus sub Direktori File dengan objek Direktori induk dan -Path, Tidak dapat memasukkan -Path dari alur dengan kecocokan jenis (string) lagi.

#### <a name="before"></a>Sebelumnya

```powershell
PS C:\> $dir = Get-AzStorageFile -ShareName $shareName -Path testdir -Context $ctx

PS C:\> @('dir1', 'dir2') | Remove-AzStorageDirectory -Directory $dir
```

#### <a name="after"></a>Sesudahnya

```powershell
PS C:\> $dir = Get-AzStorageFile -ShareName $shareName -Path testdir -Context $ctx

PS C:\> $paths = @(
    [PSCustomObject]@{  Path = 'dir1 }
    [PSCustomObject]@{ Path = 'dir2' }
)

PS C:\> $paths | Remove-AzStorageDirectory -Directory $dir.CloudFileDirectory
```
