---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Billing.dll-Help.xml
Module Name: Az.Billing
online version: https://docs.microsoft.com/powershell/module/az.billing/get-azbillingprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-AzBillingProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-AzBillingProfile.md
ms.openlocfilehash: 82eceb0d524b0ffdc7e77e49930880ae150d8331
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142434548"
---
# Get-AzBillingProfile

## SYNOPSIS
Dapatkan profil tagihan.

## SYNTAX

### Daftar (Default)
```
Get-AzBillingProfile -BillingAccountName <String> -BillingProfileName <String> [-ExpandInvoiceSection]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Satu
```
Get-AzBillingProfile -BillingAccountName <String> -BillingProfileName <String> -Name <System.Collections.Generic.List`1[System.String]> [-ExpandInvoiceSection]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzBillingProfile** mendapatkan profil tagihan di bawah akun tagihan tertentu. 

## EXAMPLES

### Contoh 1
```powershell
Get-AzBillingProfile -BillingAccountName 00000000-0000-0000-0000-000000000000
```

Dapatkan semua profil tagihan di bawah akun tagihan tertentu.

### Contoh 2
```powershell
Get-AzBillingProfile -BillingAccountName 00000000-0000-0000-0000-000000000000 -Name AAAA-0A00-AAA-ZZZ
```

Dapatkan profil tagihan dengan nama yang ditentukan.

### Contoh 3
```powershell
Get-AzBillingProfile -BillingAccountName 00000000-0000-0000-0000-000000000000 -ExpandInvoiceSection
```

Dapatkan semua profil tagihan di bawah akun tagihan tertentu, dan sertakan bagian faktur dalam hasilnya.

### Contoh 4
```powershell
Get-AzBillingProfile -BillingAccountName 00000000-0000-0000-0000-000000000000 -ExpandInvoiceSection -Name <System.Collections.Generic.List`1[System.String]>
```

Dapatkan profil tagihan dengan nama yang ditentukan, dan sertakan bagian faktur dalam hasil.

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

### -ExpandInvoiceSection
Sertakan bagian faktur di bawah profil tagihan.

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

### -Nama
Nama profil tagihan tertentu.

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

### Microsoft.Azure.Commands.Billing.Models.PSBillingProfile

## CATATAN

## RELATED LINKS
