---
external help file: ''
Module Name: Az.Quota
online version: https://docs.microsoft.com/powershell/module/az.quota/new-azquota
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/New-AzQuota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/New-AzQuota.md
ms.openlocfilehash: 76f48847e33cc2fdf8ff20025a6f4e41d40c6270
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142166544"
---
# New-AzQuota

## SYNOPSIS
Buat atau perbarui batas kuota untuk sumber daya tertentu dengan nilai yang diminta.
Untuk memperbarui kuota, ikuti langkah-langkah ini:\n1.
Gunakan operasi GET untuk kuota dan penggunaan untuk menentukan berapa banyak sisa kuota untuk sumber daya tertentu dan untuk menghitung batas kuota baru.
Langkah-langkah ini dirinci dalam [contoh ini](https://techcommunity.microsoft.com/t5/azure-governance-and-management/using-the-new-quota-rest-api/ba-p/2183670).\n2.
Gunakan operasi PUT ini untuk memperbarui batas kuota.
Silakan periksa URI di header lokasi untuk status detail permintaan.

## SYNTAX

```
New-AzQuota -ResourceName <String> -Scope <String> [-Limit <ILimitJsonObject>] [-Name <String>]
 [-ResourceType <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Buat atau perbarui batas kuota untuk sumber daya tertentu dengan nilai yang diminta.
Untuk memperbarui kuota, ikuti langkah-langkah ini:\n1.
Gunakan operasi GET untuk kuota dan penggunaan untuk menentukan berapa banyak sisa kuota untuk sumber daya tertentu dan untuk menghitung batas kuota baru.
Langkah-langkah ini dirinci dalam [contoh ini](https://techcommunity.microsoft.com/t5/azure-governance-and-management/using-the-new-quota-rest-api/ba-p/2183670).\n2.
Gunakan operasi PUT ini untuk memperbarui batas kuota.
Silakan periksa URI di header lokasi untuk status detail permintaan.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui batas kuota untuk sumber daya tertentu dengan nilai yang diminta
```powershell
$limit = New-AzQuotaLimitObject -Value 1003
New-AzQuota -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus2" -ResourceName "PublicIPAddresses" -Name "PublicIPAddresses" -Limit $limit
```

```output
Name              NameLocalizedValue          Unit  ETag
----              ------------------          ----  ----
PublicIPAddresses Public IP Addresses - Basic Count
```

Perintah ini membuat atau memperbarui batas kuota untuk sumber daya tertentu dengan nilai yang diminta.

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
Parameter Sets: (All)
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
Parameter Sets: (All)
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Quota.Models.Api20210315Preview.ICurrentQuotaLimitBase

## CATATAN

ALIAS

## RELATED LINKS

