---
external help file: ''
Module Name: Az.Quota
online version: https://docs.microsoft.com/powershell/module/az.quota/get-azquota
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Get-AzQuota.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Quota/help/Get-AzQuota.md
ms.openlocfilehash: 5c6989b866732b9f35145a83cd64807ef64a7f11
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143277299"
---
# Get-AzQuota

## SYNOPSIS
Dapatkan batas kuota sumber daya.
Respons dapat digunakan untuk menentukan sisa kuota untuk menghitung batas kuota baru yang dapat dikirimkan dengan permintaan PUT.

## SYNTAX

### Daftar (Default)
```
Get-AzQuota -Scope <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Mendapatkan
```
Get-AzQuota -ResourceName <String> -Scope <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzQuota -InputObject <IQuotaIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan batas kuota sumber daya.
Respons dapat digunakan untuk menentukan sisa kuota untuk menghitung batas kuota baru yang dapat dikirimkan dengan permintaan PUT.

## EXAMPLES

### Contoh 1: Mencantumkan batas kuota lingkup
```powershell
Get-AzQuota -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus"
```

```output
Name                                                ResourceGroupName Unit  ETag
----                                                ----------------- ----  ----
VirtualNetworks                                                       Count
StaticPublicIPAddresses                                               Count
NetworkSecurityGroups                                                 Count
PublicIPAddresses                                                     Count
CustomIpPrefixes                                                      Count
PublicIpPrefixes                                                      Count
```

Perintah ini mencantumkan batas kuota lingkup.

### Contoh 2: Dapatkan batas kuota sumber daya
```powershell
Get-AzQuota -Scope "subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/providers/Microsoft.Network/locations/eastus" -ResourceName "MinPublicIpInterNetworkPrefixLength"
```

```output
Name                                NameLocalizedValue        Unit  ETag
----                                ------------------        ----  ----
MinPublicIpInterNetworkPrefixLength Public IPv4 Prefix Length Count
```

Perintah ini mendapatkan batas kuota sumber daya.
Respons dapat digunakan untuk menentukan sisa kuota untuk menghitung batas kuota baru yang dapat dikirimkan dengan permintaan PUT.

## PARAMETERS

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
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceName
Nama sumber daya untuk penyedia sumber daya tertentu.
Misalnya:
- Nama SKU untuk Microsoft.Compute
- SKU atau TotalLowPriorityCores untuk Microsoft.MachineLearningServices Untuk Microsoft.Network PublicIPAddresses.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
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
Parameter Sets: Get, List
Aliases:

Required: True
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

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IQuotaIdentity>: Parameter Identitas
  - `[Id <String>]`: ID permintaan kuota.
  - `[Id1 <String>]`: Jalur identitas sumber daya
  - `[ResourceName <String>]`: Nama sumber daya untuk penyedia sumber daya tertentu. Misalnya: - Nama SKU untuk Microsoft.Compute - SKU atau TotalLowPriorityCores untuk Microsoft.MachineLearningServices Untuk Microsoft.Network PublicIPAddresses.
  - `[Scope <String>]`: Target URI sumber daya Azure. Misalnya, `/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/qms-test/providers/Microsoft.Batch/batchAccounts/testAccount/`. Ini adalah URI sumber daya Azure target untuk operasi List GET. Jika ditambahkan `{resourceName}` setelah `/quotas`, maka ini adalah URI sumber daya Azure target dalam operasi GET untuk sumber daya tertentu.

## RELATED LINKS

