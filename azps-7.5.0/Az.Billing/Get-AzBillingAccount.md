---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Billing.dll-Help.xml
Module Name: Az.Billing
online version: https://docs.microsoft.com/powershell/module/az.billing/get-azbillingaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-AzBillingAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Billing/Billing/help/Get-AzBillingAccount.md
ms.openlocfilehash: cdc59c3712d5a7ad4900ee392a477e5051a434b3
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145730890"
---
# Get-AzBillingAccount

## SYNOPSIS
Mendapatkan akun penagihan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.billing/get-azbillingaccount) untuk informasi terbaru.

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
Cmdlet **Get-AzBillingAccount** mendapatkan akun penagihan, yang dapat diakses pengguna. 

## EXAMPLES

### Contoh 1
```powershell
Get-AzBillingAccount
```

Dapatkan semua akun penagihan yang dapat diakses pengguna.

### Contoh 2
```powershell
Get-AzBillingAccount -Name 00000000-0000-0000-0000-000000000000
```

Dapatkan akun penagihan dengan nama yang ditentukan.

### Contoh: 3
```powershell
Get-AzBillingAccount -IncludeAddress
```

Dapatkan semua akun penagihan yang dapat diakses pengguna, dan sertakan alamat dalam hasilnya.

### Contoh 4
```powershell
Get-AzBillingAccount -ExpandBillingProfile
```

Dapatkan semua akun penagihan yang dapat diakses pengguna, dan sertakan profil penagihan dalam hasilnya.

### Contoh 5
```powershell
Get-AzBillingAccount -ExpandInvoiceSection
```

Dapatkan semua akun penagihan yang dapat diakses pengguna, dan sertakan profil penagihan dan bagian faktur di bawahnya dalam hasilnya.

### Contoh 6
```powershell
Get-AzBillingAccount -ExpandInvoiceSection -IncludeAddress -ExpandBillingProfile -Name 00000000-0000-0000-0000-000000000000
```

Dapatkan akun penagihan dengan nama yang ditentukan, dan sertakan alamat, profil penagihan, dan bagian faktur di bawahnya dalam hasilnya.

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
Sertakan alamat akun penagihan.

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
Sertakan profil penagihan di bawah akun penagihan.

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
Sertakan profil penagihan di bawah bagian akun penagihan dan faktur di bawahnya.

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

### -Name
Nama akun penagihan tertentu.

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
Cantumkan entitas penagihan di bawah akun penagihan yang dapat digunakan sebagai input untuk membuat langganan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Billing.Models.PSBillingAccount

## NOTES

## RELATED LINKS
