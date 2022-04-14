---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: 5E854358-CA9D-4336-BA6A-BF7B1FADAB50
online version: https://docs.microsoft.com/powershell/module/az.monitor/new-azactivitylogalertcondition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzActivityLogAlertCondition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzActivityLogAlertCondition.md
ms.openlocfilehash: 0ef47d11be07d4669f4ce99c2fa9c3e5070655f9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142177387"
---
# New-AzActivityLogAlertCondition

## SYNOPSIS
Membuat objek kondisi peringatan log aktivitas baru dalam memori.

## SYNTAX

```
New-AzActivityLogAlertCondition -Field <String> -Equal <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzActivityLogAlertCondition** membuat objek kondisi peringatan log aktivitas baru dalam memori.

## EXAMPLES

### Contoh 1: Membuat objek kondisi peringatan log aktivitas baru dalam memori.
```powershell
$Condition = New-AzActivityLogAlertCondition -Field "Requests" -Equal "OtherField"
Write-Host "Field property value: $($Condition.Field)"
Write-Host "Equals property value: $($Condition.Equals)"
```

```output
Field property value: Requests
Equals property value: OtherField
```

Perintah ini membuat objek kondisi peringatan log aktivitas baru dalam memori.
**CATATAN**: ketika cmdlet ini digunakan dengan [Set-AzActivityLogAlert](https://docs.microsoft.com/powershell/module/az.monitor/set-azactivitylogalert) setidaknya salah satu objek ini, yang diteruskan sebagai parameter, harus memiliki Bidang yang sama dengan "Kategori". Jika tidak, backend merespons dengan 400 (BadRequest.)

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

### -Sama dengan
Menentukan properti yang sama dengan untuk kondisi daun.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Field
Menentukan bidang untuk kondisi tersebut.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.Monitor.Management.Models.ActivityLogAlertLeafCondition

## CATATAN

## RELATED LINKS

[Set-AzActivityLogAlert](./Set-AzActivityLogAlert.md)

[Enable-AzActivityLogAlert](./Enable-AzActivityLogAlert.md)

[Disable-AzActivityLogAlert](./Disable-AzActivityLogAlert.md)

[Get-AzActivityLogAlert](./Get-AzActivityLogAlert.md)

[Hapus-AzActivityLogAlert](./Remove-AzActivityLogAlert.md)

[Grup Baru-AzAction](./Get-AzActionGroup.md)
