---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataShare.dll-Help.xml
Module Name: Az.DataShare
online version: https://docs.microsoft.com/powershell/module/az.datashare/remove-azdatashare
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataShare/DataShare/help/Remove-AzDataShare.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataShare/DataShare/help/Remove-AzDataShare.md
ms.openlocfilehash: 8d4788e0ef259e3c14ac93f8514ac290ff408d11
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145747540"
---
# Remove-AzDataShare

## SYNOPSIS
Menghapus berbagi data.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.datashare/remove-azdatashare) untuk informasi terbaru.

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
```powershell
Remove-AzDataShare -ResourceGroupName "ADS" -AccountName "WikiAds" -Name "AdsShare"
```

```output
Are you sure you want to remove data share "AdsShare"? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

Perintah ini menghapus berbagi data bernama AdsShare dari akun berbagi data Azure WikiAds. 

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

Diperlukan: Posisi Benar: Nilai default bernama: Tidak Ada Terima input alur: True (ByValue) Terima karakter wildcard: False

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

### -Name
Nama berbagi data Azure

Jenis yaml: Set Parameter String: ByFieldsParameterSet Alias: 

Diperlukan: Posisi Benar: Nilai default bernama: Tidak Ada Terima input alur: False Terima karakter kartubebas: False

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

Jenis yaml: Set Parameter SwitchParameter: (Semua) Alias: 

Diperlukan: Posisi Salah: Nilai default bernama: Tidak Ada Terima input alur: False Terima karakter kartubebas: False

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
Nama grup sumber daya akun berbagi data azure

Jenis yaml: Set Parameter String: ByFieldsParameterSet Alias: 

Diperlukan: Posisi Benar: Nilai default bernama: Tidak Ada Terima input alur: False Terima karakter kartubebas: False

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

Jenis yaml: Set Parameter String: ByResourceIdParameterSet Alias: 

Diperlukan: Posisi Benar: Nilai default bernama: Tidak Ada Terima input alur: True (ByPropertyName) Terima karakter kartubebas: False

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

Jenis yaml: Set Parameter SwitchParameter: (Semua) Alias: cf

Diperlukan: Posisi Salah: Nilai default bernama: Tidak Ada Terima input alur: False Terima karakter kartubebas: False

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

Jenis yaml: Set Parameter SwitchParameter: (Semua) Alias: wi

Diperlukan: Posisi Salah: Nilai default bernama: Tidak Ada Terima input alur: False Terima karakter kartubebas: False




Jenis yaml: Microsoft.Azure.PowerShell.Cmdlets.DataShare.Models.PSDataShare Parameter Sets: ByObjectParameterSet Aliases:

Diperlukan: Posisi Benar: Nilai default bernama: Tidak Ada Terima input alur: True (ByValue) Terima karakter wildcard: False

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

### Microsoft.Azure.PowerShell.Cmdlets.DataShare.Models.PSDataShare

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
