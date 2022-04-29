---
external help file: ''
Module Name: Az.DiskPool
online version: https://docs.microsoft.com/powershell/module/az.diskpool/stop-azdiskpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Stop-AzDiskPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DiskPool/help/Stop-AzDiskPool.md
ms.openlocfilehash: dce5de32816fd40c11a707886d7099fcd9b8986f
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144225603"
---
# Stop-AzDiskPool

## SYNOPSIS
Mematikan Kumpulan Disk dan melepaskan sumber daya komputasi.
Anda tidak ditagih untuk sumber daya komputasi yang digunakan Kumpulan Disk ini.
Operasi ini bisa memakan waktu 10 menit untuk menyelesaikannya.
Ini adalah perilaku layanan yang diharapkan.

## SYNTAX

### Batalkan alokasi (Default)
```
Stop-AzDiskPool -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeallocateViaIdentity
```
Stop-AzDiskPool -InputObject <IDiskPoolIdentity> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mematikan Kumpulan Disk dan melepaskan sumber daya komputasi.
Anda tidak ditagih untuk sumber daya komputasi yang digunakan Kumpulan Disk ini.
Operasi ini bisa memakan waktu 10 menit untuk menyelesaikannya.
Ini adalah perilaku layanan yang diharapkan.

## EXAMPLES

### Contoh 1: Menghentikan Kumpulan Disk
```powershell
Stop-AzDiskPool -Name 'disk-pool-1' -ResourceGroupName 'storagepool-rg-test'
```

Perintah ini membatalkan alokasi Kumpulan Disk.

### Contoh 2: Hentikan Kumpulan Disk menurut objek
```powershell
Get-AzDiskPool -Name 'disk-pool-1' -ResourceGroupName 'storagepool-rg-test' | Stop-AzDiskPool
```

Perintah ini membatalkan alokasi Kumpulan Disk berdasarkan objek.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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
Type: Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.IDiskPoolIdentity
Parameter Sets: DeallocateViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama Kumpulan Disk.

```yaml
Type: System.String
Parameter Sets: Deallocate
Aliases:

Required: True
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

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -ResourceGroupName
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: Deallocate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: Deallocate
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DiskPool.Models.IDiskPoolIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDiskPoolIdentity>: Parameter Identitas
  - `[DiskPoolName <String>]`: Nama Kumpulan Disk.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[IscsiTargetName <String>]`: Nama Target iSCSI.
  - `[Location <String>]`: Lokasi sumber daya.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

