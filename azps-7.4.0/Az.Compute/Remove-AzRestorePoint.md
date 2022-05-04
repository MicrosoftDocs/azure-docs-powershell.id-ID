---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/remove-azrestorepoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzRestorePoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Remove-AzRestorePoint.md
ms.openlocfilehash: bc974e60d71580fc1a4b1523544988307e300265
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144633122"
---
# Remove-AzRestorePoint

## SYNOPSIS
Cmdlet ini dapat menghapus Titik Pemulihan 

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/remove-azrestorepoint) untuk informasi terbaru.

## SYNTAX

```
Remove-AzRestorePoint [-ResourceGroupName] <String> [-RestorePointCollectionName] <String> [-Name] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini dapat menghapus Titik Pemulihan 

## EXAMPLES

### Contoh 1
```powershell
Remove-AzRestorePoint -ResourceGroupName <String> -RestorePointCollectionName <String> -Name <String> -Confirm
```

Gunakan ini untuk Menghapus Titik Pemulihan

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama sumber daya

```yaml
Type: String
Parameter Sets: (All)
Aliases: RestorePointName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RestorePointCollectionName
Nama Kumpulan Titik Pemulihan 

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
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

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSRestorePoint

## NOTES

## RELATED LINKS
