---
external help file: ''
Module Name: Az.Quota
online version: https://docs.microsoft.com/powershell/module/az.quota/update-azquota
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Update-AzQuota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Update-AzQuota.md
ms.openlocfilehash: 9474e6a0cdec6e5db8690640c3e9b9725e66dee7
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140196390"
---
# Update-AzQuota

## SYNOPSIS
Perbarui batas kuota untuk sumber daya tertentu ke nilai tertentu:\n1.
Gunakan operasi Usages-GET dan Quota-GET untuk menentukan sisa kuota sumber daya tertentu dan untuk menghitung batas kuota baru.
Langkah-langkah ini dijelaskan secara [mendetail dalam contoh ini](https://techcommunity.microsoft.com/t5/azure-governance-and-management/using-the-new-quota-rest-api/ba-p/2183670).\n2.
Gunakan operasi PUT ini untuk memperbarui batas kuota.
Silakan periksa URI di header lokasi untuk status mendetail permintaan tersebut.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzQuota -ResourceName <String> -Scope <String> [-Limit <ILimitJsonObject>] [-Name <String>]
 [-ResourceType <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzQuota -InputObject <IQuotaIdentity> [-Limit <ILimitJsonObject>] [-Name <String>]
 [-ResourceType <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Perbarui batas kuota untuk sumber daya tertentu ke nilai tertentu:\n1.
Gunakan operasi Usages-GET dan Quota-GET untuk menentukan sisa kuota sumber daya tertentu dan untuk menghitung batas kuota baru.
Langkah-langkah ini dijelaskan secara [mendetail dalam contoh ini](https://techcommunity.microsoft.com/t5/azure-governance-and-management/using-the-new-quota-rest-api/ba-p/2183670).\n2.
Gunakan operasi PUT ini untuk memperbarui batas kuota.
Silakan periksa URI di header lokasi untuk status mendetail permintaan tersebut.

## EXAMPLES

### Contoh 1: Perbarui batas kuota untuk sumber daya tertentu dengan nilai yang ditentukan
```powershell
PS C:\> $limit = New-AzQuotaLimitObject -Value 1001
PS C:\> Update-AzQuota -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus2" -ResourceName "PublicIPAddresses" -Name "PublicIPAddresses" -Limit $limit

Name              NameLocalizedValue          UsageUsagesType UsageValue ETag
----              ------------------          --------------- ---------- ----
PublicIPAddresses Public IP Addresses - Basic                 0
```

Perintah ini memperbarui batas kuota untuk sumber daya tertentu ke nilai yang ditentukan.

### Contoh 2: Memperbarui batas kuota untuk sumber daya tertentu ke nilai tertentu melalui pipeline
```powershell
PS C:\> 
PS C:\> $limit = New-AzQuotaLimitObject -Value 1007
PS C:\> Get-AzQuota -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus2" -ResourceName "PublicIPAddresses" | Update-AzQuota -Name "PublicIPAddresses" -Limit $limit

Name              NameLocalizedValue          UsageUsagesType UsageValue ETag
----              ------------------          --------------- ---------- ----
PublicIPAddresses Public IP Addresses - Basic                 0
```

Perintah ini memperbarui batas kuota untuk sumber daya tertentu ke nilai tertentu menurut saluran.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Quota.Models.IQuotaIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Limit
Properti batas kuota sumber daya.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Quota.Models.Api20210315Preview.ILimitJsonObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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

### -ResourceName
Nama sumber daya untuk penyedia sumber daya tertentu.
Misalnya:
- Nama SKU untuk Microsoft.Compute
- SKU atau TotalLowPriorityCores untuk Microsoft.MachineLearningServices For Microsoft.Network PublicIPAddresses.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceType
Nama tipe sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
URI sumber daya Azure target.
Misalnya, `/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/qms-test/providers/Microsoft.Batch/batchAccounts/testAccount/`.
Ini adalah URI sumber daya Azure target untuk operasi GET Daftar.
Jika ditambahkan `{resourceName}` setelah `/quotas`, itu adalah URI sumber daya Azure target dalam operasi DAPATKAN untuk sumber daya tertentu.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
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

### Microsoft.Azure.PowerShell.Cmdlets.Quota.Models.IQuotaIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Quota.Models.Api20210315Preview.ICurrentQuotaLimitBase

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IQuotaIdentity>: Parameter Identitas
  - `[Id <String>]`: ID permintaan kuota.
  - `[Id1 <String>]`: Jalur identitas sumber daya
  - `[ResourceName <String>]`: Nama sumber daya untuk penyedia sumber daya tertentu. Misalnya: - Nama SKU untuk Microsoft.Compute - SKU atau TotalLowPriorityCores untuk Microsoft.MachineLearningServices For Microsoft.Network PublicIPAddresses.
  - `[Scope <String>]`: URI sumber daya Azure target. Misalnya, `/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/qms-test/providers/Microsoft.Batch/batchAccounts/testAccount/`. Ini adalah URI sumber daya Azure target untuk operasi GET Daftar. Jika ditambahkan `{resourceName}` setelah `/quotas`, itu adalah URI sumber daya Azure target dalam operasi DAPATKAN untuk sumber daya tertentu.

## RELATED LINKS

