---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
ms.assetid: 4A91EEDA-D8F0-4109-A32E-B83694952C06
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/disable-azoperationalinsightslinuxsyslogcollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Disable-AzOperationalInsightsLinuxSyslogCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Disable-AzOperationalInsightsLinuxSyslogCollection.md
ms.openlocfilehash: 73d6d4750bbcd6c39d038a0605ec310941c85f6f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143312363"
---
# Disable-AzOperationalInsightsLinuxSyslogCollection

## SYNOPSIS
Menghentikan pengumpulan data syslog dari komputer Linux.

## SYNTAX

### ByWorkspaceName (Default)
```
Disable-AzOperationalInsightsLinuxSyslogCollection [-ResourceGroupName] <String> [-WorkspaceName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByWorkspaceObject
```
Disable-AzOperationalInsightsLinuxSyslogCollection [-Workspace] <PSWorkspace>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Disable-AzOperationalInsightsLinuxSyslogCollection** menghentikan pengumpulan data syslog dari komputer Linux yang terhubung dalam ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Disable-AzOperationalInsightsLinuxSyslogCollection -ResourceGroupName test-rg -WorkspaceName OperationalInsights-1
```

```output
Name              : DataSource_LinuxSyslogCollection
ResourceGroupName : test-rg
WorkspaceName     : OperationalInsights-1
ResourceId        : /subscriptions/xxxx-xxxx-xxxx-xxxx-xxxx/resourceGroups/test-rg/providers/Microsoft.OperationalInsights/wo
                    rkspaces/OperationalInsights-1/datasources/DataSource_LinuxSyslogCollection
Kind              : LinuxSyslogCollection
Properties        : {"state":"Disabled"} 
```
Menghentikan pengumpulan data syslog dari komputer Linux yang terhubung dalam ruang kerja.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi komputer Linux.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ruang Kerja
Menentukan ruang kerja tempat cmdlet ini beroperasi.

```yaml
Type: Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace
Parameter Sets: ByWorkspaceObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama Ruang Kerja
Menentukan nama ruang kerja tempat cmdlet ini beroperasi.

```yaml
Type: System.String
Parameter Sets: ByWorkspaceName
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSDataSource

## NOTES
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, operasional, wawasan

## RELATED LINKS

[Enable-AzOperationalInsightsLinuxSyslogCollection](./Enable-AzOperationalInsightsLinuxSyslogCollection.md)

[New-AzOperationalInsightsLinuxSyslogDataSource](./New-AzOperationalInsightsLinuxSyslogDataSource.md)


