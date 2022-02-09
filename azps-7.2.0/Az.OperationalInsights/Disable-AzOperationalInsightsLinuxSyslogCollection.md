---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
ms.assetid: 4A91EEDA-D8F0-4109-A32E-B83694952C06
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/disable-azoperationalinsightslinuxsyslogcollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Disable-AzOperationalInsightsLinuxSyslogCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Disable-AzOperationalInsightsLinuxSyslogCollection.md
ms.openlocfilehash: 2431ff2ae3a5dd17ab8ac0e3fa103a68724c41ac
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138269979"
---
# Disable-AzOperationalInsightsLinuxSyslogCollection

## SYNOPSIS
Berhenti pengumpulan data syslog dari komputer Linux.

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
Cmdlet **Disable-AzOperationalInsightsLinuxSyslogCollection** menghentikan kumpulan data syslog dari komputer Linux yang tersambung di dalam ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Disable-AzOperationalInsightsLinuxSyslogCollection -ResourceGroupName yuzhi-rg -WorkspaceName OperationalInsights-1

Name              : DataSource_LinuxSyslogCollection
ResourceGroupName : yuzhi-rg
WorkspaceName     : OperationalInsights-1
ResourceId        : /subscriptions/0b1f6471-1bf0-4dda-aec3-cb9272f09590/resourceGroups/yuzhi-rg/providers/Microsoft.OperationalInsights/wo
                    rkspaces/OperationalInsights-1/datasources/DataSource_LinuxSyslogCollection
Kind              : LinuxSyslogCollection
Properties        : {"state":"Disabled"} 
```
Berhenti pengumpulan data syslog dari komputer Linux yang tersambung di sebuah ruang kerja.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Menentukan ruang kerja tempat cmdlet beroperasi.

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

### -WorkspaceName
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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSWorkspace

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSDataSource

## CATATAN
* Kata kunci: azure, azurerm, arm, resource, management, manager, operational, insights

## RELATED LINKS

[Enable-AzOperationalInsightsLinuxSyslogCollection](./Enable-AzOperationalInsightsLinuxSyslogCollection.md)

[New-AzOperationalInsightsLinuxSyslogDataSource](./New-AzOperationalInsightsLinuxSyslogDataSource.md)


