---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/remove-azdatacollectionruleassociation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Remove-AzDataCollectionRuleAssociation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Remove-AzDataCollectionRuleAssociation.md
ms.openlocfilehash: 24dc3c51234fafe16b02badb6d31e27b708fdaf9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141910101"
---
# Remove-AzDataCollectionRuleAssociation

## SYNOPSIS
Menghapus kaitan aturan pengumpulan data.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.monitor/remove-azdatacollectionruleassociation) untuk informasi terbaru.

## SYNTAX

### ByName (Default)
```
Remove-AzDataCollectionRuleAssociation
      -TargetResourceId <string> 
      -AssociationName <string> 
      [-PassThru]
      [-DefaultProfile <IAzureContextContainer>]
      [-WhatIf]
      [-Confirm]
      [<CommonParameters>]
```

### ByInputObject
```
Remove-AzDataCollectionRuleAssociation
      -InputObject <PSDataCollectionRuleAssociationProxyOnlyResource>
      [-PassThru]
      [-DefaultProfile <IAzureContextContainer>]
      [-WhatIf]
      [-Confirm]
      [<CommonParameters>]
```

### ByResourceId
```
Remove-AzDataCollectionRuleAssociation
      -AssociationId <string>
      [-PassThru]
      [-DefaultProfile <IAzureContextContainer>]
      [-WhatIf]
      [-Confirm]
      [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzDataCollectionRuleAssociation** menghapus asosiasi aturan pengumpulan data (DCRA).

Untuk menerapkan DCR ke mesin virtual, Anda membuat asosiasi untuk mesin virtual. Mesin virtual mungkin memiliki hubungan dengan beberapa DCR, dan DCR mungkin memiliki beberapa mesin virtual yang terkait dengannya. Ini memungkinkan Anda menentukan sekumpulan DCR, masing-masing cocok dengan persyaratan tertentu, dan menerapkannya hanya ke mesin virtual tempatnya diterapkan. Berikut adalah [artikel "Mengonfigurasi pengumpulan data untuk agen Azure Monitor"](https://docs.microsoft.com/azure/azure-monitor/platform/data-collection-rule-azure-monitor-agent) menggunakan DCRA.

## EXAMPLES

### Contoh 1: Hapus aturan pengumpulan data yang terkait dengan parameter nama dan ID sumber daya target (mesin virtual terkait)
```
PS C:\>Remove-AzDataCollectionRuleAssociation -TargetResourceId $vm.Id -AssociationName $assocName
```

### Contoh 2: Menghapus aturan pengumpulan data dengan Objek Input
```
PS C:\>$dcrAssoc | Remove-AzDataCollectionRule
```

### Contoh 3: Menghapus aturan pengumpulan data dengan properti ID sumber daya asosiasi
```
PS C:\>Remove-AzDataCollectionRule -AssociationId $dcrAssoc.Id
```

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

### -TargetResourceId
ID sumber daya terkait.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases: ResourceUri

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AssociationName
Nama sumber daya asosiasi.

```yaml
Type: System.String
Parameter Sets: ByName (Default)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek PSDataCollectionRuleResource

```yaml
Type: Microsoft.Azure.Commands.Insights.OutputClasses.PSDataCollectionRuleAssociationProxyOnlyResource
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -AssociationId
Pengidentifikasi sumber daya.

```yaml
Type: System.String
Parameter Sets: ByResourceId
Aliases: ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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

### System.String
###Microsoft.Azure.Commands. Insights. OutputClasses.PSDataCollectionRuleAssociationProxyOnlyResource

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS

[Get-AzDataCollectionRule](./Get-AzDataCollectionRule.md)
 [New-AzDataCollectionRule](./New-AzDataCollectionRule.md)
