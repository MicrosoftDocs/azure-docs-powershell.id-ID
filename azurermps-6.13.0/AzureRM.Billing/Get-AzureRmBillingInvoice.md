---
external help file: Microsoft.Azure.Commands.Billing.dll-Help.xml
Module Name: AzureRM.Billing
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.billing/get-azurermbillinginvoice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Billing/Commands.Billing/help/Get-AzureRmBillingInvoice.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Billing/Commands.Billing/help/Get-AzureRmBillingInvoice.md
ms.openlocfilehash: 1f21022294b1bcf5c75a7cf49dcc009600dc4cc0
ms.sourcegitcommit: ea4f0db405efec935ac72601b51807dbb45674c9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/28/2022
ms.locfileid: "140865098"
---
# Get-AzureRmBillingInvoice

## SYNOPSIS
Dapatkan faktur tagihan langganan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Daftar (Default)
```
Get-AzureRmBillingInvoice [-MaxCount <Int32>] [-GenerateDownloadUrl] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### Terbaru
```
Get-AzureRmBillingInvoice [-Latest] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Tunggal
```
Get-AzureRmBillingInvoice -Name <System.Collections.Generic.List`1[System.String]>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmBillingInvoice** mendapatkan faktur tagihan langganan. 

## EXAMPLES

### Contoh 1
```
PS C:\> Get-AzureRmBillingInvoice -Latest
```

Dapatkan faktur langganan terbaru.

### Contoh 2
```
PS C:\> Get-AzureRmBillingInvoice -Name 2017-02-18-432543543
```

Dapatkan faktur langganan dengan nama yang ditentukan.

### Contoh 3
```
PS C:\> Get-AzureRmBillingInvoice
```

Dapatkan semua faktur langganan yang tersedia dalam urutan kronologis terbalik yang dimulai dengan faktur terbaru tanpa Url unduhan. 

### Contoh 4
```
PS C:\> Get-AzureRmBillingInvoice -GenerateDownloadUrl -MaxCount 10
```

Dapatkan 10 faktur terbaru dari langganan dan sertakan Url unduhan dalam hasil.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GenerateDownloadUrl
Buat url unduhan faktur.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Terbaru
Dapatkan faktur terbaru.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Latest
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxCount
Menentukan jumlah maksimum rekaman untuk dikembalikan.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama faktur tertentu untuk mendapatkan atau yang paling baru jika tidak ditentukan.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: Single
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Billing.Models.PSInvoice

## CATATAN

## RELATED LINKS
