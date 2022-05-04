---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: 85492E00-3776-4F20-A444-9C28CC6154B7
online version: https://docs.microsoft.com/powershell/module/az.monitor/get-azactivitylogalert
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzActivityLogAlert.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzActivityLogAlert.md
ms.openlocfilehash: f4b67b40c9ad8154b9f6032e525a229e408c5469
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144657918"
---
# Get-AzActivityLogAlert

## SYNOPSIS
Mendapatkan satu atau beberapa sumber daya pemberitahuan log aktivitas.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.monitor/get-azactivitylogalert) untuk informasi terbaru.

## SYNTAX

### GetByNameAndResourceGroup
```
Get-AzActivityLogAlert [-ResourceGroupName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceGroup
```
Get-AzActivityLogAlert [[-ResourceGroupName] <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzActivityLogAlert** mendapatkan satu atau beberapa sumber daya pemberitahuan log aktivitas.

## EXAMPLES

### Contoh 1: Mendapatkan pemberitahuan log aktivitas berdasarkan ID langganan
```powershell
Get-AzActivityLogAlert
```

Perintah ini mencantumkan semua pemberitahuan log aktivitas untuk langganan saat ini.

### Contoh 2: Mendapatkan pemberitahuan log aktivitas untuk grup sumber daya yang diberikan
```powershell
Get-AzActivityLogAlert -ResourceGroupName "Default-activityLogAlerts"
```

Perintah ini mencantumkan pemberitahuan log aktivitas untuk grup sumber daya tertentu.

### Contoh 3: Dapatkan pemberitahuan log aktivitas.
```powershell
Get-AzActivityLogAlert -ResourceGroupName "Default-activityLogAlerts" -Name "alert1"
```

Perintah ini mencantumkan satu (daftar dengan satu elemen) pemberitahuan log aktivitas.

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

### -Name
Nama pemberitahuan log aktivitas.

```yaml
Type: System.String
Parameter Sets: GetByNameAndResourceGroup
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya pemberitahuan berada.
Jika Nama tidak null atau kosong, parameter ini harus berisi dan string yang tidak kosong.

```yaml
Type: System.String
Parameter Sets: GetByNameAndResourceGroup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: GetByResourceGroup
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSActivityLogAlertResource

## NOTES

## RELATED LINKS

[Set-AzActivityLogAlert](./Set-AzActivityLogAlert.md)

[Remove-AzActivityLogAlert](./Remove-AzActivityLogAlert.md)

[New-AzActionGroup](./New-AzActionGroup.md)

[New-AzActivityLogAlertCondition](./New-AzActivityLogAlertCondition.md)
