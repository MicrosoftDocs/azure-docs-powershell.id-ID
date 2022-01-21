---
external help file: ''
Module Name: Az.Functions
online version: https://docs.microsoft.com/powershell/module/az.functions/update-azfunctionappplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Update-AzFunctionAppPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Update-AzFunctionAppPlan.md
ms.openlocfilehash: 47b38cedbdb7dac9e1b640ccc9b89792870efd7b
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136556287"
---
# Update-AzFunctionAppPlan

## SYNOPSIS
Memperbarui paket layanan aplikasi fungsi.

## SYNTAX

### ByName (Default)
```
Update-AzFunctionAppPlan -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>] [-Force]
 [-MaximumWorkerCount <Int32>] [-MinimumWorkerCount <Int32>] [-Sku <String>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### ByObjectInput
```
Update-AzFunctionAppPlan -InputObject <IAppServicePlan> [-Force] [-MaximumWorkerCount <Int32>]
 [-MinimumWorkerCount <Int32>] [-Sku <String>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui paket layanan aplikasi fungsi.

## EXAMPLES

### Contoh 1: Update an app service plan to EP2 sku with twenty maximum workers.
```powershell
PS C:\> Update-AzFunctionAppPlan -ResourceGroupName MyResourceGroupName `
                                 -Name MyPremiumPlan `
                                 -MaximumWorkerCount 20 `
                                 -Sku EP2 `
                                 -Force

```

Perintah ini memperbarui paket layanan aplikasi untuk EP2 sku dengan dua puluh pekerja maksimal.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan.

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

### -Force
Memaksa cmdlet untuk memperbarui paket aplikasi fungsi tanpa meminta konfirmasi.

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

### -InputObject
Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Functions.Models.Api20190801.IAppServicePlan
Parameter Sets: ByObjectInput
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaximumWorkerCount
Jumlah maksimum pekerja untuk paket layanan aplikasi.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MaxBurst

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumWorkerCount
Jumlah minimum pekerja untuk paket layanan aplikasi.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MinInstances

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama paket Layanan Aplikasi.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron.

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
Nama grup sumber daya tempat sumber daya tersebut berada.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sku
Sku rencana.
Input yang valid adalah: EP1, EP2, EP3

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

### -SubscriptionId
ID langganan Azure.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Functions.Models.Api20190801.IAppServicePlan

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Functions.Models.Api20190801.IAppServicePlan

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IAppServicePlan> : 
  - `Location <String>`: Lokasi Sumber Daya.
  - `[Kind <String>]`: Jenis sumber daya.
  - `[Tag <IResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[Capacity <Int32?>]`: Jumlah contoh saat ini yang ditetapkan ke sumber daya.
  - `[FreeOfferExpirationTime <DateTime?>]`: Waktu saat penawaran farm gratis server kedaluwarsa.
  - `[HostingEnvironmentProfileId <String>]`: ID Sumber Daya Dari Lingkungan Layanan Aplikasi.
  - `[HyperV <Boolean?>]`: Jika paket layanan aplikasi kontainer Hyper-V, <code>true</code> <code>false</code> jika tidak.
  - `[IsSpot <Boolean?>]`: Jika <code>true</code> , Paket Layanan Aplikasi ini memiliki instans titik.
  - `[IsXenon <Boolean?>]`: Usang: Jika paket layanan aplikasi wadah Hyper-V, <code>true</code> <code>false</code> jika tidak.
  - `[MaximumElasticWorkerCount <Int32?>]`: Jumlah maksimum pekerja total yang diperbolehkan untuk Paket Layanan Aplikasi ElastisScaleEnabled ini
  - `[PerSiteScaling <Boolean?>]`: Jika <code>true</code> , aplikasi yang ditetapkan untuk paket App Service ini dapat diskalakan secara terpisah.         Jika <code>false</code> , aplikasi yang ditetapkan untuk paket Layanan Aplikasi ini akan menyesuaikan dengan semua contoh paket.
  - `[Reserved <Boolean?>]`: Jika paket layanan aplikasi <code>true</code> Linux, <code>false</code> jika tidak.
  - `[SkuCapability <ICapability[]>]`: Kemampuan SKU, misalnya, apakah manajer lalu lintas diaktifkan?
    - `[Name <String>]`: Nama kapabilitas SKU.
    - `[Reason <String>]`: Alasan kapabilitas SKU.
    - `[Value <String>]`: Nilai kapabilitas SKU.
  - `[SkuCapacityDefault <Int32?>]`: Jumlah default pekerja untuk SKU paket Layanan Aplikasi ini.
  - `[SkuCapacityMaximum <Int32?>]`: Jumlah maksimum pekerja untuk SKU paket Layanan Aplikasi ini.
  - `[SkuCapacityMinimum <Int32?>]`: Jumlah minimum pekerja untuk SKU paket Layanan Aplikasi ini.
  - `[SkuCapacityScaleType <String>]`: Konfigurasi skala yang tersedia untuk paket Layanan Aplikasi.
  - `[SkuFamily <String>]`: Kode keluarga dari SKU sumber daya.
  - `[SkuLocation <String[]>]`: Lokasi SKU.
  - `[SkuName <String>]`: Nama SKU sumber daya.
  - `[SkuSize <String>]`: Penentu ukuran SKU sumber daya.
  - `[SkuTier <String>]`: Tingkatan layanan SKU sumber daya.
  - `[SpotExpirationTime <DateTime?>]`: Waktu ketika farm server kedaluwarsa. Hanya valid jika farm merupakan farm server tempat.
  - `[TargetWorkerCount <Int32?>]`: Penskalaan jumlah pekerja.
  - `[TargetWorkerSizeId <Int32?>]`: SKALA ID ukuran pekerja.
  - `[WorkerTierName <String>]`: Tingkatan pegawai target ditetapkan ke paket Layanan Aplikasi.

## RELATED LINKS

