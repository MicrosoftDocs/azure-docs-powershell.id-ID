---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Billing.dll-Help.xml
Module Name: Az.Billing
online version: https://docs.microsoft.com/powershell/module/az.billing/get-azbillinginvoice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-AzBillingInvoice.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-AzBillingInvoice.md
ms.openlocfilehash: 2c0c7079864fd82679fd1f8e49a3205a15b696cf
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142704142"
---
# Get-AzBillingInvoice

## SYNOPSIS
Dapatkan faktur tagihan langganan.
Mendapatkan faktur tagihan akun tagihan dan profil tagihan

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.billing/get-azbillinginvoice) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzBillingInvoice [-MaxCount <Int32>] [-GenerateDownloadUrl] [-DefaultProfile <IAzureContextContainer>] [-BillingAccountName] [-BillingProfileName]
 [<CommonParameters>]
```

### Terbaru
```
Get-AzBillingInvoice [-Latest] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>] [-BillingAccountName] [-BillingProfileName]
```

### Satu
```
Get-AzBillingInvoice -Name <System.Collections.Generic.List`1[System.String]>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzBillingInvoice** mendapatkan faktur tagihan langganan. 

## EXAMPLES

### Contoh 1
```powershell
Get-AzBillingInvoice -Latest
```

Dapatkan faktur langganan terbaru.

### Contoh 2
```powershell
Get-AzBillingInvoice -Name 2017-02-18-432543543
```

Dapatkan faktur langganan dengan nama yang ditentukan.

### Contoh 3
```powershell
Get-AzBillingInvoice
```

Dapatkan semua faktur langganan yang tersedia dalam urutan kronologis terbalik dimulai dengan faktur terbaru tanpa mengunduh Url. 

### Contoh 4
```powershell
Get-AzBillingInvoice -GenerateDownloadUrl -MaxCount 10
```

Dapatkan 10 faktur terbaru langganan dan sertakan Url unduhan dalam hasilnya.

### Contoh 5
```powershell
Get-AzBillingInvoice -Name 2017-02-18-432543543 -GenerateDownloadUrl
```

Dapatkan faktur tertentu berdasarkan nama dan sertakan url unduhan dalam hasilnya.

### Contoh 6
```powershell
Get-AzBillingInvoice -BillingAccountName 00000000-0000-0000-0000-000000000000:00000000-0000-0000-0000-000000000000_0000-00-00 -GenerateDownloadUrl
```

Dapatkan faktur dengan menagih nama akun dan sertakan url unduhan untuk setiap faktur dalam hasilnya.

### Contoh 7
```powershell
Get-AzBillingInvoice -Name 0000000000 -BillingAccountName 00000000-0000-0000-0000-000000000000:00000000-0000-0000-0000-000000000000_0000-00-00 -GenerateDownloadUrl
```

Dapatkan faktur tertentu menurut nama faktur dan nama akun tagihan dan sertakan url unduh untuk setiap faktur dalam hasilnya.

### Contoh 8
```powershell
Get-AzBillingInvoice -Latest -BillingAccountName 00000000-0000-0000-0000-000000000000:00000000-0000-0000-0000-000000000000_0000-00-00 -GenerateDownloadUrl
```

Dapatkan faktur terbaru dengan menagih nama akun dan sertakan url unduhan untuk faktur dalam hasilnya.

### Contoh 9
```powershell
Get-AzBillingInvoice -GenerateDownloadUrl -BillingAccountName 00000000-0000-0000-0000-000000000000:00000000-0000-0000-0000-000000000000_0000-00-00 -BillingProfileName 0000-0000-000-000 -MaxCount 10
```

Dapatkan 10 faktur terbaru dari akun tagihan tertentu dan profil tagihan tertentu dan sertakan Url unduhan dalam hasilnya.

### Contoh 10
```powershell
Get-AzBillingInvoice -Latest -GenerateDownloadUrl -BillingAccountName 00000000-0000-0000-0000-000000000000:00000000-0000-0000-0000-000000000000_0000-00-00 -BillingProfileName 0000-0000-000-000 
```

Dapatkan faktur terbaru dengan menagih nama akun dan nama profil tagihan serta sertakan url unduhan untuk faktur dalam hasilnya.

### Contoh 11
```powershell
Get-AzBillingInvoice -BillingAccountName 00000000-0000-0000-0000-000000000000:00000000-0000-0000-0000-000000000000_0000-00-00 -BillingProfileName 0000-0000-000-000 -PeriodStartDate 0000-00-00 -PeriodEndDate 0000-00-00
```

Dapatkan faktur dengan menagih nama akun dan nama profil tagihan untuk periode tagihan yang ditentukan oleh tanggal perioStart dan tanggal periodEnd.


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

### -GenerateDownloadUrl
Buat url unduhan faktur.

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
Menentukan jumlah maksimum rekaman yang akan dikembalikan.

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
Nama faktur tertentu untuk mendapatkan atau yang terbaru jika tidak ditentukan.

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

### -BillingAccountName
Nama akun tagihan tertentu untuk mendapatkan faktur.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BillingProfileName
Nama profil tagihan tertentu untuk mendapatkan faktur.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PeriodStartDate
Tanggal mulai faktur.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PeriodEndDate
Tanggal berakhir untuk faktur.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```



### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Billing.Models.PSInvoice

## NOTES

## RELATED LINKS
