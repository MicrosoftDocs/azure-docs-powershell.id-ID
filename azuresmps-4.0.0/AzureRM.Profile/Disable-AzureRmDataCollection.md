---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: ''
schema: 2.0.0
ms.openlocfilehash: b6d907230a5bf7fb19e2b99ffa6f7fc0b24346a469e3cebb28773503203d3956
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417642"
---
# Disable-AzureRmDataCollection

## SYNOPSIS
Memilih untuk tidak mengumpulkan data untuk meningkatkan cmdlet AzurePowerShell. Data tidak dikumpulkan kecuali Anda memilih untuk ikut serta secara eksplisit.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Disable-AzureRmDataCollection [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Anda dapat meningkatkan pengalaman menggunakan Microsoft Cloud dan Azure PowerShell dengan memilih ikut serta dalam pengumpulan data.
Azure PowerShell tidak mengumpulkan data tanpa persetujuan Anda - Anda harus secara eksplisit memilih dengan menjalankan Enable-AzureRmDataCollection, atau dengan menjawab ya ketika Azure PowerShell meminta Anda tentang mengumpulkan data saat pertama kali Anda menjalankan cmdlet.
Microsoft menggabungkan data yang dikumpulkan untuk mengidentifikasi pola penggunaan, guna mengidentifikasi masalah-masalah umum dan untuk meningkatkan pengalaman penggunaan Azure PowerShell.
Microsoft Azure PowerShell tidak mengumpulkan data pribadi apa pun, atau informasi pengenal pribadi apa pun.

Jalankan cmdlet Disable-AzureRMDataCollection cmdlet untuk menonaktifkan pengumpulan data bagi pengguna saat ini.
Tindakan ini akan mencegah pengguna saat ini ditanya tentang pengumpulan data saat cmdlet pertama kali dijalankan.

Untuk mengaktifkan pengumpulan data bagi pengguna saat ini, jalankan cmdlet Enable-AzureRmDataCollection.

## EXAMPLES

### Contoh 1: Menonaktifkan pengumpulan data untuk pengguna saat ini
```
PS C:\> Disable-AzureRmDataCollection
```

Contoh ini memperlihatkan cara menonaktifkan pengumpulan data untuk pengguna saat ini. 

## PARAMETERS

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Tidak ada

## CATATAN

## RELATED LINKS

[Enable-AzureRmDataCollection]()

