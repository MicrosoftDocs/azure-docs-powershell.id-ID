---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Billing.dll-Help.xml
Module Name: Az.Billing
online version: https://docs.microsoft.com/powershell/module/az.billing/get-azbillingaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-AzBillingAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-AzBillingAccount.md
ms.openlocfilehash: bffabe09ee81db9a3389789aca4eda662308e19b
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136702987"
---
# Get-AzBillingAccount

## SYNOPSIS
Dapatkan akun tagihan.

## SYNTAX

### Daftar (Default)
```
Get-AzBillingAccount [-IncludeAddress] [-ExpandBillingProfile] [-ExpandInvoiceSection] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### Tunggal
```
Get-AzBillingAccount -Name <System.Collections.Generic.List`1[System.String]> [-IncludeAddress] [-ExpandBillingProfile] [-ExpandInvoiceSection] [-ListEntitiesToCreateSubscription]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzBillingAccount** mendapatkan akun tagihan, yang dapat diakses pengguna. 

## EXAMPLES

### Contoh 1
```
PS C:\> Get-AzBillingAccount
```

Dapatkan semua akun tagihan yang dapat diakses pengguna.

### Contoh 2
```
PS C:\> Get-AzBillingAccount -Name 00000000-0000-0000-0000-000000000000
```

Dapatkan akun tagihan dengan nama yang ditentukan.

### Contoh 3
```
PS C:\> Get-AzBillingAccount -IncludeAddress
```

Dapatkan semua akun tagihan yang bisa diakses pengguna, dan sertakan alamat dalam hasil.

### Contoh 4
```
PS C:\> Get-AzBillingAccount -ExpandBillingProfile
```

Dapatkan semua akun tagihan yang bisa diakses pengguna, dan sertakan profil tagihan dalam hasilnya.

### Contoh 5
```
PS C:\> Get-AzBillingAccount -ExpandInvoiceSection
```

Dapatkan semua akun tagihan yang bisa diakses pengguna, dan sertakan bagian profil tagihan dan faktur di bawahnya dalam hasil.

### Contoh 6
```
PS C:\> Get-AzBillingAccount -ExpandInvoiceSection -ExpandAddress -Name 00000000-0000-0000-0000-000000000000
```

Dapatkan akun tagihan dengan nama yang ditentukan, dan sertakan bagian alamat, profil tagihan dan faktur di bawahnya dalam hasil.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Daftar entitas tagihan di bawah akun tagihan yang dapat digunakan sebagai input untuk membuat langganan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Billing.Models.PSBillingAccount

## CATATAN

## RELATED LINKS
