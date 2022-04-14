---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Billing.dll-Help.xml
Module Name: Az.Billing
online version: https://docs.microsoft.com/powershell/module/az.billing/get-azbillingaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-AzBillingAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-AzBillingAccount.md
ms.openlocfilehash: 464cd5d776b450c8aca7741036b154dadda0da3a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141855194"
---
# Get-AzBillingAccount

## SYNOPSIS
Dapatkan akun tagihan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.billing/get-azbillingaccount) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzBillingAccount [-IncludeAddress] [-ExpandBillingProfile] [-ExpandInvoiceSection] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### Satu
```
Get-AzBillingAccount -Name <System.Collections.Generic.List`1[System.String]> [-IncludeAddress] [-ExpandBillingProfile] [-ExpandInvoiceSection] [-ListEntitiesToCreateSubscription]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzBillingAccount** mendapatkan akun tagihan, pengguna memiliki akses ke akun tersebut. 

## EXAMPLES

### Contoh 1
```powershell
Get-AzBillingAccount
```

Dapatkan semua akun tagihan yang dapat diakses pengguna.

### Contoh 2
```powershell
Get-AzBillingAccount -Name 00000000-0000-0000-0000-000000000000
```

Dapatkan akun tagihan dengan nama yang ditentukan.

### Contoh 3
```powershell
Get-AzBillingAccount -IncludeAddress
```

Dapatkan semua akun tagihan yang dapat diakses pengguna, dan sertakan alamat dalam hasilnya.

### Contoh 4
```powershell
Get-AzBillingAccount -ExpandBillingProfile
```

Dapatkan semua akun tagihan yang dapat diakses pengguna, dan sertakan profil tagihan dalam hasilnya.

### Contoh 5
```powershell
Get-AzBillingAccount -ExpandInvoiceSection
```

Dapatkan semua akun tagihan yang dapat diakses pengguna, serta sertakan profil tagihan dan bagian faktur di bawahnya dalam hasilnya.

### Contoh 6
```powershell
Get-AzBillingAccount -ExpandInvoiceSection -ExpandAddress -Name 00000000-0000-0000-0000-000000000000
```

Dapatkan akun tagihan dengan nama tertentu, sertakan alamat, profil tagihan, dan bagian faktur di bawahnya dalam hasilnya.

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

### -IncludeAddress
Sertakan alamat akun tagihan.

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

### -ExpandBillingProfile
Sertakan profil tagihan di bawah akun tagihan.

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

### -ExpandInvoiceSection
Sertakan profil tagihan di bawah bagian akun tagihan dan faktur di bawahnya.

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
Nama akun tagihan tertentu.

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

### -ListEntitiesToCreateSubscription
Cantumkan entitas tagihan di bawah akun tagihan yang dapat digunakan sebagai input untuk membuat langganan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Single
Aliases:

Required: False
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

### Microsoft.Azure.Commands.Billing.Models.PSBillingAccount

## CATATAN

## RELATED LINKS
