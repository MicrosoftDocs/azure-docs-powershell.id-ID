---
external help file: ''
Module Name: Az.Kusto
online version: https://docs.microsoft.com/powershell/module/az.kusto/new-azkustoscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Kusto/help/New-AzKustoScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Kusto/help/New-AzKustoScript.md
ms.openlocfilehash: 345387052acf72e9a9d0c009b2b96f97a457a702
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142424929"
---
# New-AzKustoScript

## SYNOPSIS
Membuat skrip database Kusto.

## SYNTAX

### CreateExpanded (Default)
```
New-AzKustoScript -ClusterName <String> -DatabaseName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-ContinueOnError] [-ForceUpdateTag <String>] [-ScriptUrl <String>]
 [-ScriptUrlSasToken <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### Membuat
```
New-AzKustoScript -ClusterName <String> -DatabaseName <String> -Name <String> -ResourceGroupName <String>
 -Parameter <IScript> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat skrip database Kusto.

## EXAMPLES

### Contoh 1: Membuat skrip database Kusto
```powershell
New-AzKustoScript -ClusterName testnewkustocluster -DatabaseName mykustodatabase -Name newkustoscript -ResourceGroupName testrg -ScriptUrl $BlobSASURL -ScriptUrlSasToken $BlobSASToken
```

```output
Name                                               Type
----                                               ----
testnewkustocluster/mykustodatabase/newkustoscript Microsoft.Kusto/Clusters/Databases/Scripts
```

Perintah di atas membuat skrip database Kusto bernama "newkustocript" dalam grup sumber daya "testrg".
## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -ClusterName
Nama klaster Kusto.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContinueOnError
Bendera yang menunjukkan apakah akan melanjutkan jika salah satu perintah gagal.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
Nama database dalam klaster Kusto.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceUpdateTag
String yang unik.
Jika skrip diubah akan diterapkan lagi.

```yaml
Type: System.String
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama skrip database Kusto.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ScriptName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -Parameter
Kelas mewakili skrip database.
Untuk membangun, lihat bagian CATATAN untuk properti PARAMETER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Kusto.Models.Api202101.IScript
Parameter Sets: Create
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya yang berisi klaster Kusto.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptUrl
Url untuk file blob skrip KQL.

```yaml
Type: System.String
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptUrlSasToken
Token Sas.

```yaml
Type: System.String
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Mendapatkan kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

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

### Microsoft.Azure.PowerShell.Cmdlets. Kusto. Models.Api202101.IScript

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets. Kusto. Models.Api202101.IScript

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PARAMETER <IScript>: Kelas yang mewakili skrip database.
  - `[ContinueOnError <Boolean?>]`: Bendera yang menunjukkan apakah akan melanjutkan jika salah satu perintah gagal.
  - `[ForceUpdateTag <String>]`: String yang unik. Jika skrip diubah akan diterapkan lagi.
  - `[SystemDataCreatedAt <DateTime?>]`: Stempel waktu pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Tipe identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Cap waktu modifikasi terakhir sumber daya (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir mengubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Tipe identitas yang terakhir mengubah sumber daya.
  - `[Url <String>]`: Url untuk file blob skrip KQL.
  - `[UrlSasToken <String>]`: Token SaS.

## RELATED LINKS

