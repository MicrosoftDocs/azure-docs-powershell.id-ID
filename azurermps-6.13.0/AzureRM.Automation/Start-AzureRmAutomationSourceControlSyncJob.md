---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
Module Name: AzureRM.Automation
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.automation/start-azurermautomationsourcecontrolsyncjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Automation/Commands.Automation/help/Start-AzureRmAutomationSourceControlSyncJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Automation/Commands.Automation/help/Start-AzureRmAutomationSourceControlSyncJob.md
ms.openlocfilehash: a5e9eccf464997caf427ed59e081aeb20a0da308bdbccfa751db29507e39b082
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140865152"
---
# Start-AzureRmAutomationSourceControlSyncJob

## SYNOPSIS
Memulai pekerjaan sinkronisasi kontrol sumber Otomatisasi Azure.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Start-AzureRmAutomationSourceControlSyncJob -SourceControlName <String> [-JobId <Guid>]
 [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Start-AzureRmAutomationSourceControlSyncJob memulai pekerjaan sinkronisasi kontrol sumber Azure Automation untuk nama kontrol sumber tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Start-AzureRmAutomationSourceControlSyncJob -ResourceGroupName "rg1" `
                                                    -AutomationAccountName "devAccount" `
                                                    -Name "VSTSNative"

SourceControlSyncJobId               SyncType Status  StartTime EndTime
----------------------               -------- ------  --------- -------
b51aed78-bef6-40d4-a966-cd45fd5af576 FullSync Running
```

## PARAMETERS

### -AutomationAccountName
Nama akun otomatisasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobId
Id pekerjaan sinkronisasi kontrol sumber.

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases: SourceControlSyncJobId

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceControlName
Nama kontrol sumber.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.SourceControlSyncJob

## CATATAN

## RELATED LINKS
