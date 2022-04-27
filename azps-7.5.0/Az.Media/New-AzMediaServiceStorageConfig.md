---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Media.dll-Help.xml
Module Name: Az.Media
ms.assetid: 4D64CA4D-1066-4D3E-9317-60D37D9DE2BB
online version: https://docs.microsoft.com/powershell/module/az.media/new-azmediaservicestorageconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Media/Media/help/New-AzMediaServiceStorageConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Media/Media/help/New-AzMediaServiceStorageConfig.md
ms.openlocfilehash: f77c2762efb590e3e204703fc226df5ab89fb1b6
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144112169"
---
# New-AzMediaServiceStorageConfig

## SYNOPSIS
Buat konfigurasi akun penyimpanan untuk cmdlet layanan media.

## SYNTAX

```
New-AzMediaServiceStorageConfig [-DefaultProfile <IAzureContextContainer>] [-StorageAccountId] <String>
 [-IsPrimary] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzMediaServiceStorageConfig** membuat konfigurasi akun penyimpanan untuk cmdlet layanan media.

## EXAMPLES

### Contoh 1: Membuat konfigurasi akun penyimpanan untuk cmdlet layanan media
```powershell
$StorageAccount = New-AzStorageAccount -ResourceGroupName "ResourceGroup001" -Name "Storage1" -Location "East US" -Type "Standard_GRS"

New-AzMediaServiceStorageConfig -StorageAccountId $StorageAccount.Id -IsPrimary
```

Perintah pertama membuat objek akun penyimpanan dengan menggunakan cmdlet **New-AzStorageAccount** .
Perintah menamai akun penyimpanan ini Storage1 dan jenisnya diberi nama Standard_GRS dan menyimpan hasilnya dalam variabel bernama $StorageAccount.
Perintah kedua membuat objek konfigurasi penyimpanan sebagai akun penyimpanan utama yang terkait dengan layanan media menggunakan informasi ID akun penyimpanan yang disimpan dalam variabel $StorageAccount.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsPrimary
Menunjukkan bahwa cmdlet membuat akun penyimpanan sebagai penyimpanan utama untuk layanan media.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountId
Menentukan ID akun penyimpanan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Media.Models.PSStorageAccount

## NOTES

## RELATED LINKS

[Sync-AzMediaServiceStorageKey](./Sync-AzMediaServiceStorageKey.md)


