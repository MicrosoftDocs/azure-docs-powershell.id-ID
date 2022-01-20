---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataShare.dll-Help.xml
Module Name: Az.DataShare
online version: https://docs.microsoft.com/powershell/module/az.datashare/remove-azdatashare
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataShare/DataShare/help/Remove-AzDataShare.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataShare/DataShare/help/Remove-AzDataShare.md
ms.openlocfilehash: 1440e95288c3f27a6d2f6f1f723350b8dbb1660d
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136361418"
---
# Remove-AzDataShare

## SYNOPSIS
Menghapus berbagi data.

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

### -Nama Akun
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
Azure data share object' ''yaml Type: PSDataShare Parameter Sets: ByObjectParameterSet Aliases: 

Diperlukan: Posisi True: Nilai Default Bernama: Input saluran Tidak Ada Terima: True (ByValue) Terima karakter wildcard: False

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

Tipe yaml: Kumpulan Parameter String: Alias ByFieldsParameterSet: 

Diperlukan: Posisi True: Nilai Default Bernama: Input saluran Tidak Diterima: Karakter wildcard Terima False: False

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
Objek yang dikembalikan (jika ditentukan).

Tipe yaml: SwitchParameter Parameter Sets: (Semua) Alias: 

Diperlukan: Posisi False: Nilai Default Bernama: Input saluran Tidak Terima: Karakter wildcard Terima False: False

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
Nama grup sumber daya akun berbagi data Azure

Tipe yaml: Kumpulan Parameter String: Alias ByFieldsParameterSet: 

Diperlukan: Posisi True: Nilai Default Bernama: Input saluran Tidak Diterima: Karakter wildcard Terima False: False

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

Tipe yaml: Kumpulan Parameter String: Alias ByResourceIdParameterSet: 

Diperlukan: Posisi True: Nilai Default Bernama: Input saluran Tidak Diterima: True (ByPropertyName) Terima karakter wildcard: False

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

Tipe yaml: SwitchParameter Parameter Sets: (Semua) Alias: cf

Diperlukan: Posisi False: Nilai Default Bernama: Input saluran Tidak Terima: Karakter wildcard Terima False: False

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
Cmdlet tidak berjalan.

Tipe yaml: SwitchParameter Parameter Sets: (Semua) Alias: wi

Diperlukan: Posisi False: Nilai Default Bernama: Input saluran Tidak Terima: Karakter wildcard Terima False: False




jenis yaml: Microsoft.Azure.PowerShell.Cmdlets.DataShare.Models.PSDataShare Parameter Sets: ByObjectParameterSet Aliases:

Diperlukan: Posisi True: Nilai Default Bernama: Input saluran Tidak Ada Terima: True (ByValue) Terima karakter wildcard: False

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.PowerShell.Cmdlets.DataShare.Models.PSDataShare

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
