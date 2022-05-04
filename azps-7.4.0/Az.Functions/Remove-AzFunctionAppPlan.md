---
external help file: ''
Module Name: Az.Functions
online version: https://docs.microsoft.com/powershell/module/az.functions/remove-azfunctionappplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Remove-AzFunctionAppPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Remove-AzFunctionAppPlan.md
ms.openlocfilehash: 475f51c472fe5595e32a7c8f42c4217417c33e65
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144652702"
---
# Remove-AzFunctionAppPlan

## SYNOPSIS
Menghapus paket aplikasi fungsi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.functions/remove-azfunctionappplan) untuk informasi terbaru.

## SYNTAX

### ByName (Default)
```
Remove-AzFunctionAppPlan -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>] [-Force]
 [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### ByObjectInput
```
Remove-AzFunctionAppPlan -InputObject <IAppServicePlan> [-Force] [-DefaultProfile <PSObject>] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus paket aplikasi fungsi.

## EXAMPLES

### Contoh 1: Dapatkan paket aplikasi fungsi berdasarkan nama dan hapus.
```powershell
Get-AzFunctionAppPlan -Name MyAppName -ResourceGroupName MyResourceGroupName | Remove-AzFunctionAppPlan -Force
```

Perintah ini mendapatkan paket aplikasi fungsi berdasarkan nama dan menghapusnya.

### Contoh 2: Menghapus paket aplikasi fungsi berdasarkan nama.
```powershell
Remove-AzFunctionAppPlan -Name MyAppName -ResourceGroupName MyResourceGroupName -Force
```

Perintah ini menghapus paket aplikasi fungsi berdasarkan nama.

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

### -Force
Memaksa cmdlet untuk menghapus paket aplikasi fungsi tanpa meminta konfirmasi.

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

### -Name
Nama aplikasi fungsi.

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

### -PassThru
Mengembalikan true saat perintah berhasil.

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

### System.Boolean

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

