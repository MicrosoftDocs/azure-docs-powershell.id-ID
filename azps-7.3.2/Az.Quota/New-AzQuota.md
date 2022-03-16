---
external help file: ''
Module Name: Az.Quota
online version: https://docs.microsoft.com/powershell/module/az.quota/new-azquota
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/New-AzQuota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/New-AzQuota.md
ms.openlocfilehash: 7e13d88e60c566d8f65bb82c262ee578ea3c2d8c
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140196438"
---
# New-AzQuota

## SYNOPSIS
Membuat atau memperbarui batas kuota untuk sumber daya tertentu dengan nilai yang diminta.
Untuk memperbarui kuota, ikuti langkah-langkah berikut:\n1.
Gunakan operasi GET untuk kuota dan penggunaan untuk menentukan berapa banyak sisa kuota untuk sumber daya tertentu dan untuk menghitung batas kuota baru.
Langkah-langkah ini dijelaskan secara [mendetail dalam contoh ini](https://techcommunity.microsoft.com/t5/azure-governance-and-management/using-the-new-quota-rest-api/ba-p/2183670).\n2.
Gunakan operasi PUT ini untuk memperbarui batas kuota.
Silakan periksa URI di header lokasi untuk status mendetail permintaan tersebut.

## SYNTAX

```
New-AzQuota -ResourceName <String> -Scope <String> [-Limit <ILimitJsonObject>] [-Name <String>]
 [-ResourceType <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui batas kuota untuk sumber daya tertentu dengan nilai yang diminta.
Untuk memperbarui kuota, ikuti langkah-langkah berikut:\n1.
Gunakan operasi GET untuk kuota dan penggunaan untuk menentukan berapa banyak sisa kuota untuk sumber daya tertentu dan untuk menghitung batas kuota baru.
Langkah-langkah ini dijelaskan secara [mendetail dalam contoh ini](https://techcommunity.microsoft.com/t5/azure-governance-and-management/using-the-new-quota-rest-api/ba-p/2183670).\n2.
Gunakan operasi PUT ini untuk memperbarui batas kuota.
Silakan periksa URI di header lokasi untuk status mendetail permintaan tersebut.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui batas kuota untuk sumber daya tertentu dengan nilai yang diminta
```powershell
PS C:\> $limit = New-AzQuotaLimitObject -Value 1003
PS C:\> New-AzQuota -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus2" -ResourceName "PublicIPAddresses" -Name "PublicIPAddresses" -Limit $limit

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
URI sumber daya Azure target.
Misalnya, `/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/qms-test/providers/Microsoft.Batch/batchAccounts/testAccount/`.
Ini adalah URI sumber daya Azure target untuk operasi GET Daftar.
Jika ditambahkan `{resourceName}` setelah `/quotas`, itu adalah URI sumber daya Azure target dalam operasi DAPATKAN untuk sumber daya tertentu.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Quota.Models.Api20210315Preview.ICurrentQuotaLimitBase

## CATATAN

ALIAS

## RELATED LINKS

