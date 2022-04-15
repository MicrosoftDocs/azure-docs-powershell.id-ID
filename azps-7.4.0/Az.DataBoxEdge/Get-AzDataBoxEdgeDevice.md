---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataBoxEdge.dll-Help.xml
Module Name: Az.DataBoxEdge
online version: https://docs.microsoft.com/powershell/module/az.databoxedge/get-azdataboxedgedevice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBoxEdge/DataBoxEdge/help/Get-AzDataBoxEdgeDevice.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBoxEdge/DataBoxEdge/help/Get-AzDataBoxEdgeDevice.md
ms.openlocfilehash: ef13d6cf31b3ccc6013ef8dc277d5f690b062b35
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142433098"
---
# Get-AzDataBoxEdgeDevice

## SYNOPSIS
Mendapatkan informasi tentang perangkat Box Edge Data yang tersedia.

## SYNTAX

### ListByParameterSet (Default)
```
Get-AzDataBoxEdgeDevice [[-ResourceGroupName] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByResourceIdParameterSet
```
Get-AzDataBoxEdgeDevice -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetExtendedInfoByResourceIdParameterSet
```
Get-AzDataBoxEdgeDevice -ResourceId <String> [-ExtendedInfo] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetNetworkSettingByResourceIdParameterSet
```
Get-AzDataBoxEdgeDevice -ResourceId <String> [-NetworkSetting] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetSummaryUpdateByResourceIdParameterSet
```
Get-AzDataBoxEdgeDevice -ResourceId <String> [-UpdateSummary] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetAlertByResourceIdParameterSet
```
Get-AzDataBoxEdgeDevice -ResourceId <String> [-Alert] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByNameParameterSet
```
Get-AzDataBoxEdgeDevice [-ResourceGroupName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetSummaryUpdateParameterSet
```
Get-AzDataBoxEdgeDevice [-ResourceGroupName] <String> [-Name] <String> [-UpdateSummary]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetNetworkSettingParameterSet
```
Get-AzDataBoxEdgeDevice [-ResourceGroupName] <String> [-Name] <String> [-NetworkSetting]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetExtendedInfoParameterSet
```
Get-AzDataBoxEdgeDevice [-ResourceGroupName] <String> [-Name] <String> [-ExtendedInfo]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetAlertParameterSet
```
Get-AzDataBoxEdgeDevice [-ResourceGroupName] <String> [-Name] <String> [-Alert]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDataBoxEdgeDevice** mendapatkan informasi tentang Perangkat Box Edge Data yang tersedia. Anda bisa menentukan Nama perangkat bersama dengan Nama Grup Sumber Daya untuk mendapatkan informasi di perangkat tertentu. 

## EXAMPLES

### Contoh 1
```powershell
Get-AzDataBoxEdgeDevice
```

```output
Name               ResourceGroupName  Model   Location
----               -----------------  -----   --------
deviceNameOne      resourceGroupName1 Edge    eastus
deviceNameTwo      resourceGroupName2 Edge    westus
deviceNameThree    resourceGroupName3 Gateway eastus
```

### Contoh 2
```powershell
Get-AzDataBoxEdgeDevice -ResourceId /subscriptions/subscriptionId/resourcegroups/resourceGroupName/providers/Microsoft.DataBoxEdge/dataBoxEdgeDevices/deviceName
```

```output
Name            ResourceGroupName    Model   Location
----            -----------------    -----   --------
deviceName      resourceGroupName    Edge    eastus
```

### Contoh 3
```powershell
Get-AzDataBoxEdgeDevice -ResourceGroupName resourceGroupName -Name deviceName
```

```output
Name            ResourceGroupName    Model   Location
----            -----------------    -----   --------
deviceName      resourceGroupName    Edge    eastus
```

## PARAMETERS

### -Peringatan
Mengambil pemberitahuan di perangkat edge/gateway kotak data

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetAlertByResourceIdParameterSet, GetAlertParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedInfo
Mendapatkan informasi tambahan untuk perangkat Box Edge/Gateway Kotak Data yang ditentukan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetExtendedInfoByResourceIdParameterSet, GetExtendedInfoParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Perangkat

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet, GetSummaryUpdateParameterSet, GetNetworkSettingParameterSet, GetExtendedInfoParameterSet, GetAlertParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkSetting
Mendapatkan pengaturan jaringan perangkat Box Edge/Gateway Box Data yang ditentukan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetNetworkSettingByResourceIdParameterSet, GetNetworkSettingParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: ListByParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet, GetSummaryUpdateParameterSet, GetNetworkSettingParameterSet, GetExtendedInfoParameterSet, GetAlertParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Azure ResourceId

```yaml
Type: System.String
Parameter Sets: GetByResourceIdParameterSet, GetExtendedInfoByResourceIdParameterSet, GetNetworkSettingByResourceIdParameterSet, GetSummaryUpdateByResourceIdParameterSet, GetAlertByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateSummary
Mendapatkan informasi tentang ketersediaan pembaruan berdasarkan pemindaian terakhir perangkat. Ini juga mendapatkan informasi tentang pekerjaan pengunduhan atau penginstalan yang sedang berlangsung di perangkat.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GetSummaryUpdateByResourceIdParameterSet, GetSummaryUpdateParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBoxEdge.Models.PSDataBoxEdgeDevice

### Microsoft.Azure.PowerShell.Cmdlets.DataBoxEdge.Models.PSDataBoxEdgeNetworkAdapter

### Microsoft.Azure.PowerShell.Cmdlets.DataBoxEdge.Models.PSDataBoxEdgeDeviceExtendedInfo

### Microsoft.Azure.PowerShell.Cmdlets.DataBoxEdge.Models.PSDataBoxEdgeUpdateSummary

### Microsoft.Azure.PowerShell.Cmdlets.DataBoxEdge.Models.PSDataBoxEdgeAlert

## CATATAN

## RELATED LINKS
