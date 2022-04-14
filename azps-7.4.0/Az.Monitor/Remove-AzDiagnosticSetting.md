---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: B5F2388E-0136-4F8A-8577-67CE2A45671E
online version: https://docs.microsoft.com/powershell/module/az.monitor/remove-azdiagnosticsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Remove-AzDiagnosticSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Remove-AzDiagnosticSetting.md
ms.openlocfilehash: ade516544b1983e3fc845bb15d534ec1f177b8d1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141835904"
---
# Remove-AzDiagnosticSetting

## SYNOPSIS
Menghapus pengaturan diagnostik untuk sumber daya.

## SYNTAX

### ResourceIdParameterSet (Default)
```
Remove-AzDiagnosticSetting [-Name <String>] [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SubscriptionIdParameterSet
```
Remove-AzDiagnosticSetting [-Name <String>] [-SubscriptionId] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzDiagnosticSetting** menghapus pengaturan diagnostik untuk sumber daya tertentu.
Cmdlet ini menerapkan pola ShouldProcess, yaitu mungkin meminta konfirmasi dari pengguna sebelum benar-benar membuat, mengubah, atau menghapus sumber daya.

## EXAMPLES

### Contoh 1: Menghapus pengaturan diagnostik default (layanan) untuk sumber daya
```powershell
Remove-AzDiagnosticSetting -ResourceId "Resource01"
```

Perintah ini menghapus pengaturan diagnostik default (layanan) untuk sumber daya yang disebut Resource01.

### Contoh 2: Menghapus pengaturan diagnostik default yang diidentifikasi dengan nama tertentu untuk sumber daya
```powershell
Remove-AzDiagnosticSetting -ResourceId "Resource01" -Name myDiagSetting
```

Perintah ini menghapus pengaturan diagnostik yang disebut myDiagSetting untuk sumber daya yang disebut Resource01.

## PARAMETERS

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

### -Nama
Nama pengaturan diagnostik. Jika tidak memberikan panggilan default ke "layanan" seperti dalam API sebelumnya dan cmdlet ini hanya akan menonaktifkan semua kategori untuk metrik/log.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Menentukan ID sumber daya.

```yaml
Type: System.String
Parameter Sets: ResourceIdParameterSet
Aliases: TargetResourceId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId
Id langganan

```yaml
Type: System.String
Parameter Sets: SubscriptionIdParameterSet
Aliases:

Required: True
Position: 1
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.AzureOperationResponse

## CATATAN

## RELATED LINKS

[Get-AzDiagnosticSetting](./Get-AzDiagnosticSetting.md)
 [Set-AzDiagnosticSetting](./Set-AzDiagnosticSetting.md)
