---
external help file: ''
Module Name: Azs.ContainerRegistry.Admin
online version: https://docs.microsoft.com/powershell/module/azs.containerregistry.admin/set-azscontainerregistryconfiguration
schema: 2.0.0
ms.openlocfilehash: ef2b172ffb5fe5f6ff5219151060c60a83864d43
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "136577469"
---
# Set-AzsContainerRegistryConfiguration

## SYNOPSIS
Mengonfigurasi properti konfigurasi keseluruhan registri wadah.

## SYNTAX

### PutExpanded (Default)
```
Set-AzsContainerRegistryConfiguration -ConfigurationName <String> [-Location <String>]
 [-SubscriptionId <String>] [-MaximumCapacityInGiB <Int32>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### Put
```
Set-AzsContainerRegistryConfiguration -ConfigurationName <String>
 -CONFIGURATIONOBJECT \<IContainerRegistryConfiguration> [-Location <String>] [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mengonfigurasi properti konfigurasi keseluruhan registri wadah.

## EXAMPLES

### Contoh 1: Set azs ContainerRegistry Configuration
```powershell
PS C:\> Set-AzsContainerRegistryConfiguration -MaximumCapacityInGib 30 -ConfigurationName default | ConvertTo-Json

{
    "Id":  "/subscriptions/7e41090c-4aa7-40bc-856a-a993f8fbd215/providers/Microsoft.ContainerRegistry.Admin/locations/redmond/configurations/Default",
    "MaximumCapacityInGiB":  30,
    "Name":  "redmond/Default",
    "Type":  "Microsoft.ContainerRegistry.Admin/locations/configurations"
}
```

Mengonfigurasi properti konfigurasi keseluruhan registri wadah.

## PARAMETERS

### -ConfigurationName
Nama konfigurasi.

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

### -ConfigurationObject
Properti konfigurasi registri wadah.
Untuk membuat, lihat bagian CATATAN untuk properti CONFIGURATIONOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.IContainerRegistryConfiguration
Parameter Sets: Put
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -MaximumCapacityInGiB
Total kapasitas penyimpanan (GiB) yang dapat digunakan oleh registri.

```yaml
Type: System.Int32
Parameter Sets: PutExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.IContainerRegistryConfiguration

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.IContainerRegistryConfiguration

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CONFIGURATIONOBJECT \<IContainerRegistryConfiguration> : Properti konfigurasi registri wadah.
  - `[MaximumCapacityInGiB <Int32?>]`: Total kapasitas penyimpanan (GiB) yang dapat digunakan oleh registri.

## RELATED LINKS

