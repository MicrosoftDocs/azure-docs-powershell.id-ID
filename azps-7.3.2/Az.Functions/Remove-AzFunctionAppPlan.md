---
external help file: ''
Module Name: Az.Functions
online version: https://docs.microsoft.com/powershell/module/az.functions/remove-azfunctionappplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Remove-AzFunctionAppPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Functions/help/Remove-AzFunctionAppPlan.md
ms.openlocfilehash: c78d6b054e51f2a4370b22bb7cb3fff7f1f0f263
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142889776"
---
# Remove-AzFunctionAppPlan

## SYNOPSIS
Menghapus paket aplikasi fungsi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.functions/remove-azfunctionappplan) untuk informasi terbaru.

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
PS C:\> Get-AzFunctionAppPlan -Name MyAppName -ResourceGroupName MyResourceGroupName | Remove-AzFunctionAppPlan -Force
```

Perintah ini mendapatkan rencana aplikasi fungsi berdasarkan nama dan menghapusnya.

### Contoh 2: Hapus rencana aplikasi fungsi menurut nama.
```powershell
PS C:\> Remove-AzFunctionAppPlan -Name MyAppName -ResourceGroupName MyResourceGroupName -Force
```

Perintah ini menghapus rencana aplikasi fungsi menurut nama.

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

### -Paksa
Memaksa cmdlet untuk menghapus rencana aplikasi fungsi tanpa meminta konfirmasi.

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
Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -Nama
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
  - `[HostingEnvironmentProfileId <String>]`: ID Sumber Daya lingkungan App Service.
  - `[HyperV <Boolean?>]`: Jika paket <code>true</code>layanan aplikasi kontainer Hyper-V , <code>false</code> jika tidak.
  - `[IsSpot <Boolean?>]`: Jika <code>true</code>, Paket App Service ini memiliki instans spot.
  - `[IsXenon <Boolean?>]`: Usang: Jika hyper-V container paket <code>true</code>layanan aplikasi , <code>false</code> jika tidak.
  - `[MaximumElasticWorkerCount <Int32?>]`: Jumlah maksimum total pekerja yang diperbolehkan untuk Paket App Service ElasticScaleEnabled ini
  - `[PerSiteScaling <Boolean?>]`: Jika <code>true</code>, aplikasi yang ditetapkan ke paket App Service ini dapat diskalakan secara independen.         Jika <code>false</code>, aplikasi yang ditetapkan ke paket App Service ini akan diskalakan ke semua instans paket.
  - `[Reserved <Boolean?>]`: Jika paket <code>true</code>layanan aplikasi Linux , <code>false</code> jika tidak.
  - `[SkuCapability <ICapability[]>]`: Kemampuan SKU, misalnya, apakah pengelola lalu lintas diaktifkan?
    - `[Name <String>]`: Nama kapabilitas SKU.
    - `[Reason <String>]`: Alasan kemampuan SKU.
    - `[Value <String>]`: Nilai kapabilitas SKU.
  - `[SkuCapacityDefault <Int32?>]`: Jumlah default pekerja untuk SKU paket App Service ini.
  - `[SkuCapacityMaximum <Int32?>]`: Jumlah maksimum pekerja untuk SKU paket App Service ini.
  - `[SkuCapacityMinimum <Int32?>]`: Jumlah minimum pekerja untuk SKU paket App Service ini.
  - `[SkuCapacityScaleType <String>]`: Konfigurasi skala yang tersedia untuk paket App Service.
  - `[SkuFamily <String>]`: Kode keluarga SKU sumber daya.
  - `[SkuLocation <String[]>]`: Lokasi SKU.
  - `[SkuName <String>]`: Nama SKU sumber daya.
  - `[SkuSize <String>]`: Penentu ukuran SKU sumber daya.
  - `[SkuTier <String>]`: Tingkat layanan SKU sumber daya.
  - `[SpotExpirationTime <DateTime?>]`: Waktu ketika farm server kedaluwarsa. Hanya berlaku jika ini adalah farm server spot.
  - `[TargetWorkerCount <Int32?>]`: Menghitung skala pekerja.
  - `[TargetWorkerSizeId <Int32?>]`: ID ukuran pekerja skala.
  - `[WorkerTierName <String>]`: Tingkat pekerja target ditetapkan ke paket App Service.

## RELATED LINKS

