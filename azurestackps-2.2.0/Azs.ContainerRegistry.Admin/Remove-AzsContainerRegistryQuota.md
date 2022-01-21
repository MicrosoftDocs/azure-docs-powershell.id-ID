---
external help file: ''
Module Name: Azs.ContainerRegistry.Admin
online version: https://docs.microsoft.com/powershell/module/azs.containerregistry.admin/remove-azscontainerregistryquota
schema: 2.0.0
ms.openlocfilehash: ce2b60ff0bbe3abcd2c0ec71149310415917ef65
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "136579135"
---
# Remove-AzsContainerRegistryQuota

## SYNOPSIS
Menghapus kuota registri wadah yang sudah ada

## SYNTAX

### Hapus (Default)
```
Remove-AzsContainerRegistryQuota -Name <String> [-Location <String>] [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzsContainerRegistryQuota -INPUTOBJECT \<IContainerRegistryAdminIdentity> [-DefaultProfile <PSObject>]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus kuota registri wadah yang sudah ada

## EXAMPLES

### Contoh 1: Hapus Azs ContainerRegistry Configuration
```powershell
PS C:\> Remove-AzsContainerRegistryConfiguration -ConfigurationName default 

```

Hapus konfigurasi registri wadah yang sudah ada.

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.IContainerRegistryAdminIdentity
Parameter Sets: DeleteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Nama kawasan Azure.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: False
Position: Named
Default value: (Get-AzLocation)[0].Location
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kuota registri wadah.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: QuotaName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

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

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: Delete
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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerRegistryAdmin.Models.IContainerRegistryAdminIdentity

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT \<IContainerRegistryAdminIdentity> : Parameter Identitas
  - `[CapacityName <String>]`: Nama parameter kapasitas.
  - `[ConfigurationName <String>]`: Nama konfigurasi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama kawasan Azure.
  - `[QuotaName <String>]`: Nama kuota registri wadah.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

