---
external help file: ''
Module Name: Az.Quota
online version: https://docs.microsoft.com/powershell/module/az.quota/update-azquota
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Update-AzQuota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Update-AzQuota.md
ms.openlocfilehash: 2cae2cd12b035b871add06250463b92cb439f530
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142289329"
---
# Update-AzQuota

## SYNOPSIS
Perbarui batas kuota untuk sumber daya tertentu ke nilai yang ditentukan:\n1.
Gunakan operasi Usages-GET dan Quota-GET untuk menentukan sisa kuota sumber daya tertentu dan menghitung batas kuota baru.
Langkah-langkah ini dirinci dalam [contoh ini](https://techcommunity.microsoft.com/t5/azure-governance-and-management/using-the-new-quota-rest-api/ba-p/2183670).\n2.
Gunakan operasi PUT ini untuk memperbarui batas kuota.
Silakan periksa URI di header lokasi untuk status detail permintaan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.quota/update-azquota) untuk informasi terbaru.

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
Perbarui batas kuota untuk sumber daya tertentu ke nilai yang ditentukan:\n1.
Gunakan operasi Usages-GET dan Quota-GET untuk menentukan sisa kuota sumber daya tertentu dan menghitung batas kuota baru.
Langkah-langkah ini dirinci dalam [contoh ini](https://techcommunity.microsoft.com/t5/azure-governance-and-management/using-the-new-quota-rest-api/ba-p/2183670).\n2.
Gunakan operasi PUT ini untuk memperbarui batas kuota.
Silakan periksa URI di header lokasi untuk status detail permintaan.

## EXAMPLES

### Contoh 1: Memperbarui batas kuota untuk sumber daya tertentu ke nilai yang ditentukan
```powershell
PS C:\> $limit = New-AzQuotaLimitObject -Value 1001
PS C:\> Update-AzQuota -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus2" -ResourceName "PublicIPAddresses" -Name "PublicIPAddresses" -Limit $limit

Name              NameLocalizedValue          UsageUsagesType UsageValue ETag
----              ------------------          --------------- ---------- ----
PublicIPAddresses Public IP Addresses - Basic                 0
```

Perintah ini memperbarui batas kuota untuk sumber daya tertentu ke nilai yang ditentukan.

### Contoh 2: Memperbarui batas kuota untuk sumber daya tertentu ke nilai tertentu menurut pipeline
```powershell
PS C:\> 
PS C:\> $limit = New-AzQuotaLimitObject -Value 1007
PS C:\> Get-AzQuota -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus2" -ResourceName "PublicIPAddresses" | Update-AzQuota -Name "PublicIPAddresses" -Limit $limit

Name              NameLocalizedValue          UsageUsagesType UsageValue ETag
----              ------------------          --------------- ---------- ----
PublicIPAddresses Public IP Addresses - Basic                 0
```

Perintah ini memperbarui batas kuota untuk sumber daya tertentu ke nilai tertentu menurut pipeline.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -ResourceName
Nama sumber daya untuk penyedia sumber daya tertentu.
Misalnya:
- Nama SKU untuk Microsoft.Compute
- SKU atau TotalLowPriorityCores untuk Microsoft.MachineLearningServices Untuk Microsoft.Network PublicIPAddresses.

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
Target URI sumber daya Azure.
Misalnya, `/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/qms-test/providers/Microsoft.Batch/batchAccounts/testAccount/`.
Ini adalah URI sumber daya Azure target untuk operasi List GET.
Jika ditambahkan `{resourceName}` setelah `/quotas`, maka ini adalah URI sumber daya Azure target dalam operasi GET untuk sumber daya tertentu.

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
  - `[ResourceName <String>]`: Nama sumber daya untuk penyedia sumber daya tertentu. Misalnya: - Nama SKU untuk Microsoft.Compute - SKU atau TotalLowPriorityCores untuk Microsoft.MachineLearningServices Untuk Microsoft.Network PublicIPAddresses.
  - `[Scope <String>]`: Target URI sumber daya Azure. Misalnya, `/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/qms-test/providers/Microsoft.Batch/batchAccounts/testAccount/`. Ini adalah URI sumber daya Azure target untuk operasi List GET. Jika ditambahkan `{resourceName}` setelah `/quotas`, maka ini adalah URI sumber daya Azure target dalam operasi GET untuk sumber daya tertentu.

## RELATED LINKS

