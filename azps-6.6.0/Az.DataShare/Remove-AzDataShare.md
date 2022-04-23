---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataShare.dll-Help.xml
Module Name: Az.DataShare
online version: https://docs.microsoft.com/powershell/module/az.datashare/remove-azdatashare
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataShare/DataShare/help/Remove-AzDataShare.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataShare/DataShare/help/Remove-AzDataShare.md
ms.openlocfilehash: 8addcd22e65a9cb33ac0cdcd3d2812328c324140
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143201555"
---
# Remove-AzDataShare

## SYNOPSIS
Menghapus berbagi data.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.datashare/remove-azdatashare) untuk informasi terbaru.

## SYNTAX

### ByFieldsParameterSet (Default)
```
Remove-AzDataShare -ResourceGroupName <String> -AccountName <String> -Name <String> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Remove-AzDataShare -ResourceId <String> [-PassThru] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectParameterSet
```
Remove-AzDataShare -InputObject <PSDataShare> [-PassThru] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzDataShare** menghapus berbagi data.

## EXAMPLES

### Contoh 1
```
PS C:\> Remove-AzDataShare -ResourceGroupName "ADS" -AccountName "WikiAds" -Name "AdsShare"
Are you sure you want to remove data share "AdsShare"? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

Perintah ini menghapus berbagi data bernama AdsShare dari akun berbagi data azure WikiAds. 

## PARAMETERS

### -AccountName
Nama akun berbagi data Azure

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
{{Fill AsJob Description}}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
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

### -InputObject
Objek berbagi data Azure' ''yaml Type: PSDataShare Parameter Sets: ByObjectParameterSet Aliases: 

Diperlukan: True Position: Nilai default bernama: None Accept pipeline input: True (ByValue) Accept wildcard characters: False

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataShare.Models.PSDataShare
Parameter Sets: ByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama berbagi data Azure

yaml Type: String Parameter Sets: ByFieldsParameterSet Aliases: 

Diperlukan: Posisi True: Nilai default bernama: Tidak Ada Menerima input pipeline: False Terima karakter wildcard: False

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek (jika ditentukan).

Tipe yaml: Set Parameter SwitchParameter: (Semua) Alias: 

Diperlukan: Posisi False: Nilai default bernama: Tidak Ada Terima input pipeline: False Terima karakter wildcard: False

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya dari akun berbagi data azure

yaml Type: String Parameter Sets: ByFieldsParameterSet Aliases: 

Diperlukan: Posisi True: Nilai default bernama: Tidak Ada Menerima input pipeline: False Terima karakter wildcard: False

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya berbagi data Azure

yaml Type: String Parameter Sets: ByResourceIdParameterSet Aliases: 

Diperlukan: True Position: Nilai default bernama: None Accept pipeline input: True (ByPropertyName) Accept wildcard characters: False

```yaml
Type: System.String
Parameter Sets: ByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

Tipe yaml: Set Parameter SwitchParameter: (Semua) Alias: cf

Diperlukan: Posisi False: Nilai default bernama: Tidak Ada Terima input pipeline: False Terima karakter wildcard: False

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

tipe yaml: Set Parameter SwitchParameter: (Semua) Alias: wi

Diperlukan: Posisi False: Nilai default bernama: Tidak Ada Terima input pipeline: False Terima karakter wildcard: False




tipe yaml: Microsoft.Azure.PowerShell.Cmdlets.DataShare.Models.PSDataShare Parameter Set: ByObjectParameterSet Aliases:

Diperlukan: True Position: Nilai default bernama: None Accept pipeline input: True (ByValue) Accept wildcard characters: False

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

### Microsoft.Azure.PowerShell.Cmdlets.DataShare.Models.PSDataShare

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
