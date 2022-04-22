---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: ''
schema: 2.0.0
ms.openlocfilehash: d0aaa631bcaade8fef0454adf9c2429d0e1563e8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142978607"
---
# Disable-AzureRmDataCollection

## SYNOPSIS
Menolak pengumpulan data untuk menyempurnakan cmdlet AzurePowerShell. Data tidak dikumpulkan kecuali Anda memilih untuk ikut serta secara eksplisit.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Disable-AzureRmDataCollection [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Anda dapat meningkatkan pengalaman menggunakan Microsoft Cloud dan Azure PowerShell dengan memilih pengumpulan data.
Azure PowerShell tidak mengumpulkan data tanpa persetujuan Anda - Anda harus secara eksplisit ikut serta dengan menjalankan Enable-AzureRmDataCollection, atau dengan menjawab ya ketika Azure PowerShell meminta Anda mengumpulkan data pada kali pertama Anda menjalankan cmdlet.
Microsoft menggabungkan data yang dikumpulkan untuk mengidentifikasi pola penggunaan, mengidentifikasi masalah umum dan meningkatkan pengalaman menggunakan Azure PowerShell.
Microsoft Azure PowerShell tidak mengumpulkan data pribadi apa pun, atau informasi pribadi apa pun.

Jalankan cmdlet Disable-AzureRMDataCollection untuk menonaktifkan pengumpulan data bagi pengguna saat ini.
Ini akan mencegah pengguna saat ini diminta tentang pengumpulan data pada cmdlet pertama kali dijalankan.

Untuk mengaktifkan pengumpulan data bagi pengguna saat ini, jalankan cmdlet Enable-AzureRmDataCollection.

## EXAMPLES

### Contoh 1: Menonaktifkan pengumpulan data untuk pengguna saat ini
```
PS C:\> Disable-AzureRmDataCollection
```

Contoh ini memperlihatkan cara menonaktifkan pengumpulan data untuk pengguna saat ini. 

## PARAMETERS

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Tidak

## NOTES

## RELATED LINKS

[Enable-AzureRmDataCollection]()

