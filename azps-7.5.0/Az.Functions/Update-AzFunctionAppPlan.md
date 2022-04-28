---
external help file: ''
Module Name: Az.Functions
online version: https://docs.microsoft.com/powershell/module/az.functions/update-azfunctionappplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Update-AzFunctionAppPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Update-AzFunctionAppPlan.md
ms.openlocfilehash: cdd26ad1430c2c4e1e8c286f9c833610aeac049e
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144215234"
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

### Contoh 1: Perbarui paket layanan aplikasi ke sku EP2 dengan dua puluh pekerja maksimum.
```powershell
Update-AzFunctionAppPlan -ResourceGroupName MyResourceGroupName `
                         -Name MyPremiumPlan `
                         -MaximumWorkerCount 20 `
                         -Sku EP2 `
                         -Force
```

Perintah ini memperbarui paket layanan aplikasi ke sku EP2 dengan dua puluh pekerja maksimum.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan.

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
Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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

### -Name
Nama paket App Service.

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
Nama grup sumber daya tempat sumber daya berada.

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
Rencana sku.
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
Atur ID Langganan Azure.

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

### Microsoft.Azure.PowerShell.Cmdlets.Functions.Models.Api20190801.IAppServicePlan

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Functions.Models.Api20190801.IAppServicePlan

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IAppServicePlan>: 
  - `Location <String>`: Lokasi Sumber Daya.
  - `[Kind <String>]`: Jenis sumber daya.
  - `[Tag <IResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[Capacity <Int32?>]`: Jumlah instans saat ini yang ditetapkan ke sumber daya.
  - `[FreeOfferExpirationTime <DateTime?>]`: Waktu ketika penawaran gratis farm server kedaluwarsa.
  - `[HostingEnvironmentProfileId <String>]`: ID sumber daya lingkungan App Service.
  - `[HyperV <Boolean?>]`: Jika hyper-V paket <code>true</code>layanan aplikasi kontainer , <code>false</code> jika tidak.
  - `[IsSpot <Boolean?>]`: Jika <code>true</code>, App Service Plan ini memiliki instans spot.
  - `[IsXenon <Boolean?>]`: Usang: Jika paket <code>true</code>layanan aplikasi kontainer Hyper-V , <code>false</code> jika tidak.
  - `[MaximumElasticWorkerCount <Int32?>]`: Jumlah maksimum total pekerja yang diizinkan untuk Paket App Service ElasticScaleEnabled ini
  - `[PerSiteScaling <Boolean?>]`: Jika <code>true</code>, aplikasi yang ditetapkan ke paket App Service ini dapat diskalakan secara independen.         Jika <code>false</code>, aplikasi yang ditetapkan ke paket App Service ini akan menskalakan ke semua instans paket.
  - `[Reserved <Boolean?>]`: Jika paket <code>true</code>layanan aplikasi Linux, <code>false</code> jika tidak.
  - `[SkuCapability <ICapability[]>]`: Kemampuan SKU, misalnya, apakah traffic manager diaktifkan?
    - `[Name <String>]`: Nama kemampuan SKU.
    - `[Reason <String>]`: Alasan kemampuan SKU.
    - `[Value <String>]`: Nilai kemampuan SKU.
  - `[SkuCapacityDefault <Int32?>]`: Jumlah default pekerja untuk SKU paket App Service ini.
  - `[SkuCapacityMaximum <Int32?>]`: Jumlah maksimum pekerja untuk SKU paket App Service ini.
  - `[SkuCapacityMinimum <Int32?>]`: Jumlah minimum pekerja untuk SKU paket App Service ini.
  - `[SkuCapacityScaleType <String>]`: Konfigurasi skala yang tersedia untuk paket App Service.
  - `[SkuFamily <String>]`: Kode keluarga SKU sumber daya.
  - `[SkuLocation <String[]>]`: Lokasi SKU.
  - `[SkuName <String>]`: Nama SKU sumber daya.
  - `[SkuSize <String>]`: Penentu ukuran SKU sumber daya.
  - `[SkuTier <String>]`: Tingkat layanan SKU sumber daya.
  - `[SpotExpirationTime <DateTime?>]`: Waktu ketika farm server kedaluwarsa. Valid hanya jika itu adalah farm server spot.
  - `[TargetWorkerCount <Int32?>]`: Menskalakan jumlah pekerja.
  - `[TargetWorkerSizeId <Int32?>]`: MENSKALAKAN ID ukuran pekerja.
  - `[WorkerTierName <String>]`: Tingkat pekerja target yang ditetapkan ke paket App Service.

## RELATED LINKS

