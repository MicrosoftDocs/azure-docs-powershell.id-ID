---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: B5F2388E-0136-4F8A-8577-67CE2A45671E
online version: https://docs.microsoft.com/powershell/module/az.monitor/enable-azactivitylogalert
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Enable-AzActivityLogAlert.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Enable-AzActivityLogAlert.md
ms.openlocfilehash: e9addb498f665324f540dc1149b5c42eadafffc6
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144184497"
---
# Enable-AzActivityLogAlert

## SYNOPSIS
Mengaktifkan pemberitahuan log aktivitas dan mengatur Tag-nya.

## SYNTAX

### EnableByNameAndResourceGroup
```
Enable-AzActivityLogAlert -Name <String> -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EnableByInputObject
```
Enable-AzActivityLogAlert -InputObject <PSActivityLogAlertResource> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EnableByResourceId
```
Enable-AzActivityLogAlert -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Enable-AzActivityLogAlert** memungkinkan mengaktifkan pemberitahuan log aktivitas dan mengatur tag-nya.
Cmdlet ini mengimplementasikan pola ShouldProcess, yaitu mungkin meminta konfirmasi dari pengguna sebelum benar-benar menambal sumber daya.

## EXAMPLES

### Contoh 1: Mengaktifkan pemberitahuan log aktivitas
```powershell
Enable-AzActivityLogAlert -Name "alert1" -ResourceGroupName "Default-ActivityLogsAlerts"
```

Perintah ini memungkinkan pemberitahuan log aktivitas yang disebut alert1 di grup sumber daya Default-ActivityLogsAlerts.

### Contoh 2: Mengaktifkan pemberitahuan log aktivitas menggunakan objek PSActivityLogAlertResource sebagai input
```powershell
$obj = Get-AzActivityLogAlert -ResourceGroup "Default-activityLogAlerts" -Name "alert1"
Enable-AzActivityLogAlert -InputObject $obj
```

Perintah ini memungkinkan pemberitahuan log aktivitas yang disebut alert1. Untuk ini, ia menggunakan objek PSActivityLogAlertResource sebagai argumen input.

### Contoh 3: Aktifkan ActivityLogAlert menggunakan parameter ResourceId
```powershell
Get-AzResource -ResourceGroupName "myResourceGroup" -Name "myLogAlert" | Enable-AzActivityLogAlert
```

Perintah ini memungkinkan ActivityLogAlert menggunakan parameter ResourceId dari pipa.

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

### -InputObject
Mengatur properti tag InputObject panggilan untuk mengekstrak nama yang diperlukan, nama grup sumber daya, dan properti tag opsional.

```yaml
Type: Microsoft.Azure.Commands.Insights.OutputClasses.PSActivityLogAlertResource
Parameter Sets: EnableByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama pemberitahuan log aktivitas.

```yaml
Type: System.String
Parameter Sets: EnableByNameAndResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya pemberitahuan akan ada.

```yaml
Type: System.String
Parameter Sets: EnableByNameAndResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Mengatur properti tag ResourceId dari panggilan untuk mengekstrak nama yang diperlukan, properti nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: EnableByResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands. Insights. OutputClasses.PSActivityLogAlertResource

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSActivityLogAlertResource

## NOTES

## RELATED LINKS

[Set-AzActivityLogAlert](./Set-AzActivityLogAlert.md)

[Get-AzActivityLogAlert](./Get-AzActivityLogAlert.md)

[Remove-AzActivityLogAlert](./Remove-AzActivityLogAlert.md)

[New-AzActionGroup](./New-AzActionGroup.md)

[New-AzActivityLogAlertCondition](./New-AzActivityLogAlertCondition.md)

[Disable-AzActivityLogAlert](./Disable-AzActivityLogAlert.md)
