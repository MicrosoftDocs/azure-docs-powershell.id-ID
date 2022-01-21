---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/new-azfrontdoorcdnorigingroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnOriginGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/New-AzFrontDoorCdnOriginGroup.md
ms.openlocfilehash: 48c04d21d6c60d9276d6f8ed710127526bfec6ae
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136538900"
---
# New-AzFrontDoorCdnOriginGroup

## SYNOPSIS
Membuat grup origin.

## SYNTAX

```
New-AzFrontDoorCdnOriginGroup [-AdditionalLatencyInMillisecond <Int32>] -OriginGroupName <String>
 [-ProbeIntervalInSeconds <Int32>] [-ProbePath <String>] [-ProbeProtocol <String>] [-ProbeRequestType <String>]
 -ProfileName <String> -ResourceGroupName <String> [-SampleSize <Int32>] [-SuccessfulSamplesRequired <Int32>]
 [-TrafficRestorationTimeToHealedOrNewEndpointsInMinutes <Int32>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat grup origin.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzFrontDoorCdnOriginGroup -OriginGroupName $originGroupName -ProfileName $profileName -ResourceGroupName $resourceGroupName
```

Membuat grup origin.

## PARAMETERS

### -AdditionalLatencyInMillisecond
Latensi tambahan dalam milidetik agar belanda masuk ke dalam wadah latensi terendah.

```yaml
Type: Int32
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OriginGroupName
Nama grup origin Pintu Depan Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllahIntervalInSeconds
Jumlah detik antara health transit.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Jalur relatif terhadap origin yang digunakan untuk menentukan kesehatan origin.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Yamaprotocol
Protokol untuk digunakan dalam protokol kesehatan.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestRequestType
Tipe permintaan kesehatan yang dibuat.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileName
Nama profil Pintu Depan Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SampleSize
Jumlah sampel yang dipertimbangkan untuk memuat keputusan keseimbangan.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SuccessfulSamplesRequired
Jumlah sampel dalam periode sampel yang harus berhasil.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficRestorationTimeToHealedOrNewEndpointsInMinutes
Waktu dalam hitungan menit untuk menggeser lalu lintas ke titik akhir secara bertahap ketika titik akhir yang tidak sehat menjadi sehat atau titik akhir baru ditambahkan.

```yaml
Type: Int32
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
Type: SwitchParameter
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
Type: SwitchParameter
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.AfdModels.PSAfdOriginGroup

## CATATAN

## RELATED LINKS
