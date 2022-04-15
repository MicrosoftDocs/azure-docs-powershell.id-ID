---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
Module Name: AzureRM.Profile
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.profile/enable-azurermdatacollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Profile/Commands.Profile/help/Enable-AzureRmDataCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Profile/Commands.Profile/help/Enable-AzureRmDataCollection.md
ms.openlocfilehash: 83c7bda6c7b41f857bac9b63afcca07baa6ecd93
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142136402"
---
# Enable-AzureRmDataCollection

## SYNOPSIS
Memungkinkan Azure PowerShell mengumpulkan data untuk meningkatkan pengalaman pengguna dengan cmdlet AzurePowerShell.
Menjalankan cmdlet ini memilih pengumpulan data untuk pengguna saat ini di komputer saat ini.
Tidak ada data yang dikumpulkan kecuali Anda memilih untuk ikut serta secara eksplisit.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Enable-AzureRmDataCollection [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Anda dapat meningkatkan pengalaman menggunakan Microsoft Cloud dan Azure PowerShell dengan memilih pengumpulan data.
Azure PowerShell tidak mengumpulkan data tanpa persetujuan Anda - Anda harus secara eksplisit ikut serta dengan menjalankan Enable-AzureRmDataCollection, atau dengan menjawab ya ketika Azure PowerShell meminta Anda mengumpulkan data pada kali pertama Anda menjalankan cmdlet.
Microsoft menggabungkan data yang dikumpulkan untuk mengidentifikasi pola penggunaan, mengidentifikasi masalah umum dan meningkatkan pengalaman menggunakan Azure PowerShell.
Microsoft Azure PowerShell tidak mengumpulkan data pribadi apa pun, atau informasi pribadi apa pun.
Jalankan cmdlet Enable-AzureRMDataCollection untuk mengaktifkan pengumpulan data bagi pengguna saat ini di komputer saat ini.
Ini akan mencegah pengguna saat ini diminta tentang pengumpulan data pada cmdlet pertama kali dijalankan.
Untuk menonaktifkan pengumpulan data bagi pengguna saat ini, jalankan cmdlet Disable-AzureRmDataCollection.

## EXAMPLES

### Contoh 1: Mengaktifkan pengumpulan data untuk pengguna saat ini
```
PS C:\> Enable-AzureRmDataCollection
```

Contoh ini memperlihatkan cara mengaktifkan pengumpulan data untuk pengguna saat ini.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Nonaktifkan-AzureRmDataCollection](./Disable-AzureRmDataCollection.md)

