---
external help file: ''
Module Name: Azs.ContainerRegistry.Admin
online version: https://docs.microsoft.com/powershell/module/azs.containerregistry.admin/set-azscontainerregistryconfiguration
schema: 2.0.0
ms.openlocfilehash: ef2b172ffb5fe5f6ff5219151060c60a83864d43
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142911899"
---
# Set-AzsContainerRegistryConfiguration

## SYNOPSIS
Mengonfigurasi registri kontainer keseluruhan properti konfigurasi.

## SYNTAX

### PutExpanded (Default)
```
Set-AzsContainerRegistryConfiguration -ConfigurationName <String> [-Location <String>]
 [-SubscriptionId <String>] [-MaximumCapacityInGiB <Int32>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### Menempatkan
```
Set-AzsContainerRegistryConfiguration -ConfigurationName <String>
 -CONFIGURATIONOBJECT \<IContainerRegistryConfiguration> [-Location <String>] [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mengonfigurasi registri kontainer keseluruhan properti konfigurasi.

## EXAMPLES

### Contoh 1: Atur Azs ContainerRegistry Configuration
```powershell
PS C:\> Set-AzsContainerRegistryConfiguration -MaximumCapacityInGib 30 -ConfigurationName default | ConvertTo-Json

{
    "Id":  "/subscriptions/7e41090c-4aa7-40bc-856a-a993f8fbd215/providers/Microsoft.ContainerRegistry.Admin/locations/redmond/configurations/Default",
    "MaximumCapacityInGiB":  30,
    "Name":  "redmond/Default",
    "Type":  "Microsoft.ContainerRegistry.Admin/locations/configurations"
}
```

Mengonfigurasi registri kontainer keseluruhan properti konfigurasi.

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
Properti konfigurasi registri kontainer.
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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.IContainerRegistryConfiguration

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.Api20191101Preview.IContainerRegistryConfiguration

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CONFIGURATIONOBJECT \<IContainerRegistryConfiguration>: Properti konfigurasi registri kontainer.
  - `[MaximumCapacityInGiB <Int32?>]`: Total kapasitas penyimpanan (GiB) yang dapat digunakan oleh registri.

## RELATED LINKS

