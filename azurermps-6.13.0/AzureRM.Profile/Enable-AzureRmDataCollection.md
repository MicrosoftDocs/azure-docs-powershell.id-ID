---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
Module Name: AzureRM.Profile
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.profile/enable-azurermdatacollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Profile/Commands.Profile/help/Enable-AzureRmDataCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Profile/Commands.Profile/help/Enable-AzureRmDataCollection.md
ms.openlocfilehash: ee29a4b3d04299f81a6bffb445f69b23b79b3f23ca4ae6b2c4b64c0bd454a945
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132413926"
---
# Enable-AzureRmDataCollection

## SYNOPSIS
Memungkinkan Azure PowerShell mengumpulkan data untuk meningkatkan pengalaman pengguna dengan cmdlet AzurePowerShell.
Menjalankan cmdlet ini memungkinkan pengumpulan data untuk pengguna saat ini di komputer saat ini.
Tidak ada data yang dikumpulkan kecuali Anda memilih untuk ikut serta secara eksplisit.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Enable-AzureRmDataCollection [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Anda dapat meningkatkan pengalaman menggunakan Microsoft Cloud dan Azure PowerShell dengan memilih ikut serta dalam pengumpulan data.
Azure PowerShell tidak mengumpulkan data tanpa persetujuan Anda - Anda harus secara eksplisit memilih dengan menjalankan Enable-AzureRmDataCollection, atau dengan menjawab ya ketika Azure PowerShell meminta Anda tentang mengumpulkan data saat pertama kali Anda menjalankan cmdlet.
Microsoft menggabungkan data yang dikumpulkan untuk mengidentifikasi pola penggunaan, guna mengidentifikasi masalah-masalah umum dan untuk meningkatkan pengalaman penggunaan Azure PowerShell.
Microsoft Azure PowerShell tidak mengumpulkan data pribadi apa pun, atau informasi pengenal pribadi apa pun.
Jalankan cmdlet Enable-AzureRMDataCollection mengaktifkan pengumpulan data untuk pengguna saat ini di komputer saat ini.
Tindakan ini akan mencegah pengguna saat ini ditanya tentang pengumpulan data saat cmdlet pertama kali dijalankan.
Untuk menonaktifkan pengumpulan data bagi pengguna saat ini, jalankan cmdlet Disable-AzureRmDataCollection.

## EXAMPLES

### Contoh 1: Mengaktifkan pengumpulan data untuk pengguna saat ini
```
PS C:\> Enable-AzureRmDataCollection
```

Contoh ini memperlihatkan cara mengaktifkan pengumpulan data untuk pengguna saat ini.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
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

### Tidak ada

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Disable-AzureRmDataCollection](./Disable-AzureRmDataCollection.md)

