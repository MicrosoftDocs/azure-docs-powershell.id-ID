---
external help file: ''
Module Name: Azs.ContainerRegistry.Admin
online version: https://docs.microsoft.com/powershell/module/azs.containerregistry.admin/new-azscontainerregistryquota
schema: 2.0.0
ms.openlocfilehash: ebdd48d8b9cebb399a39b8da465117598da29cce
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141812066"
---
# New-AzsContainerRegistryQuota

## SYNOPSIS
Membuat atau memperbarui kuota registri kontainer yang sudah ada.

## SYNTAX

### CreateExpanded (Default)
```
New-AzsContainerRegistryQuota -Name <String> [-Location <String>] [-SubscriptionId <String>]
 [-CapacityPerRegistryInGiB <Int32>] [-NumberOfRegistry <Int32>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### Membuat
```
New-AzsContainerRegistryQuota -Name <String> -QUOTAOBJECT \<IContainerRegistryQuota> [-Location <String>]
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui kuota registri kontainer yang sudah ada.

## EXAMPLES

### Contoh 1: New Azs ContainerRegistry Quota
```powershell
PS C:\> New-AzsContainerRegistryQuota -QuotaName testquota -CapacityPerRegistryInGib 20 -NumberOfRegistry 20 | ConvertTo-Json

{
    "CapacityPerRegistryInGiB":  20,
    "Id":  "/subscriptions/7e41090c-4aa7-40bc-856a-a993f8fbd215/providers/Microsoft.ContainerRegistry.Admin/locations/redmond/quotas/testquota",
    "Name":  "redmond/testquota",
    "NumberOfRegistry":  20,
    "Type":  "Microsoft.ContainerRegistry.Admin/locations/quotas"
}
```

Membuat atau memperbarui kuota registri kontainer yang sudah ada.

## PARAMETERS

### -CapacityPerRegistryInGiB
Storage kapasitas (GiB) setiap registri.

```yaml
Type: System.Int32
Parameter Sets: CreateExpanded
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

### -Lokasi
Nama kawasan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzLocation)[0].Location
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kuota registri kontainer.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: QuotaName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfRegistry
Jumlah total akun registri kontainer.

```yaml
Type: System.Int32
Parameter Sets: CreateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -QuotaObject
Kuota registri kontainer.
Untuk membangun, lihat bagian CATATAN untuk properti QUOTAOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.IContainerRegistryQuota
Parameter Sets: Create
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.IContainerRegistryQuota

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.IContainerRegistryQuota

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


KUOTAOBJECT \<IContainerRegistryQuota>: Kuota registri kontainer.
  - `[CapacityPerRegistryInGiB <Int32?>]`: Storage kapasitas (GiB) dari setiap registri.
  - `[NumberOfRegistry <Int32?>]`: Total jumlah akun registri kontainer.

## RELATED LINKS

