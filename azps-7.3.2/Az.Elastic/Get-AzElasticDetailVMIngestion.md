---
external help file: ''
Module Name: Az.Elastic
online version: https://docs.microsoft.com/powershell/module/az.elastic/get-azelasticdetailvmingestion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/Get-AzElasticDetailVMIngestion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Elastic/help/Get-AzElasticDetailVMIngestion.md
ms.openlocfilehash: 1fe744735028a646ea064001126b2935d8056af9
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140200247"
---
# Get-AzElasticDetailVMIngestion

## SYNOPSIS
Daftar detail vm ingestion yang akan dipantau oleh sumber daya monitor Elastis.

## SYNTAX

### Detail (Default)
```
Get-AzElasticDetailVMIngestion -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DetailsViaIdentity
```
Get-AzElasticDetailVMIngestion -InputObject <IElasticIdentity> [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Daftar detail vm ingestion yang akan dipantau oleh sumber daya monitor Elastis.

## EXAMPLES

### Contoh 1: Detail daftar vm ingestion yang akan dipantau oleh sumber daya monitor Elastis
```powershell
PS C:\> Get-AzElasticDetailVMIngestion -ResourceGroupName elastic-rg-3eytki -Name elastic-rhqz1v

CloudId                                  IngestionKey
-------                                  ------------
elastic-rhqz1v:xxxxxxxxxxxxxxxxxxxxxxxxx xxxxxxxxxxxxxxxxxxxxxxx
```

Perintah ini mencantumkan detail vm ingestion yang akan dipantau oleh sumber daya monitor Elastis.

### Contoh 2: Detail daftar vm ingestion yang akan dipantau oleh sumber daya monitor Elastis menurut pipeline
```powershell
PS C:\> Get-AzElasticMonitor -ResourceGroupName elastic-rg-3eytki -Name elastic-rhqz1v | Get-AzElasticDetailVMIngestion

CloudId                                  IngestionKey
-------                                  ------------
elastic-rhqz1v:xxxxxxxxxxxxxxxxxxxxxxxxx xxxxxxxxxxxxxxxxxxxxxxx
```

Perintah ini mencantumkan detail vm ingestion yang akan dipantau oleh sumber daya monitor Elastis melalui pipeline.

## PARAMETERS

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

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Elastic.Models.IElasticIdentity
Parameter Sets: DetailsViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Memantau nama sumber daya

```yaml
Type: System.String
Parameter Sets: Details
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat sumber daya Elastis dimiliki.

```yaml
Type: System.String
Parameter Sets: Details
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan Azure.
Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-00000000000)

```yaml
Type: System.String[]
Parameter Sets: Details
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Elastis.Models.IElasticIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Elastis.Models.Api20200701.IVMIngestionDetailsResponse

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IElasticIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MonitorName <String>]`: Memantau nama sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya tempat sumber daya Elastis dimiliki.
  - `[RuleSetName <String>]`: Nama sumber daya Kumpulan Aturan Tag
  - `[SubscriptionId <String>]`: ID langganan Azure. Ini adalah string yang diformat GUID (misalnya 00000000-0000-0000-0000-00000000000)

## RELATED LINKS

