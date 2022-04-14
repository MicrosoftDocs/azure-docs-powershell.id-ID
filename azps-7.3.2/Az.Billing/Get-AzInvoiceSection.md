---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Billing.dll-Help.xml
Module Name: Az.Billing
online version: https://docs.microsoft.com/powershell/module/az.billing/get-azinvoicesection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-AzInvoiceSection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-AzInvoiceSection.md
ms.openlocfilehash: b19e799b396ea7d75122608d36487e9b5e578e1c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142218997"
---
# Get-AzInvoiceSection

## SYNOPSIS
Dapatkan bagian faktur.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.billing/get-azinvoicesection) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzInvoiceSection -BillingAccountName <String> -BillingProfileName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### Satu
```
Get-AzInvoiceSection -BillingAccountName <String> -BillingProfileName <String> -Name <System.Collections.Generic.List`1[System.String]>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzInvoiceSection** mendapatkan bagian faktur di bawah profil tagihan tertentu. 

## EXAMPLES

### Contoh 1
```powershell
Get-AzInvoiceSection -BillingAccountName 00000000-0000-0000-0000-000000000000 -BillingProfileName AAAA-0A00-AAA-ZZZ
```

Dapatkan semua bagian faktur di bawah profil tagihan tertentu.

### Contoh 2
```powershell
Get-AzInvoiceSection -BillingAccountName 00000000-0000-0000-0000-000000000000 -BillingProfileName AAAA-0A00-AAA-ZZZ -Name BBBB-0A00-BBB-ZZZ
```

Dapatkan bagian faktur dengan nama yang ditentukan.

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

### -BillingAccountName
Nama akun tagihan tertentu.

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

### -BillingProfileName
Nama profil tagihan tertentu.

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

### -Nama
Nama bagian faktur tertentu.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Billing.Models.PSInvoiceSection

## CATATAN

## RELATED LINKS
