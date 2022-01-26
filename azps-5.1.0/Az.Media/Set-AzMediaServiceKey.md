---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Media.dll-Help.xml
Module Name: Az.Media
ms.assetid: D28EB28D-DBC6-48D5-AB0A-C56F56CD0104
online version: https://docs.microsoft.com/en-us/powershell/module/az.media/set-azmediaservicekey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Media/Media/help/Set-AzMediaServiceKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Media/Media/help/Set-AzMediaServiceKey.md
ms.openlocfilehash: 44c1ff2fe283e3cd804d20a8df21023b3c222150
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136020289"
---
# Set-AzMediaServiceKey

## SYNOPSIS
Meregenerasi kunci yang digunakan untuk mengakses titik akhir REST yang terkait dengan layanan media.

## SINTAKS

```
Set-AzMediaServiceKey [-ResourceGroupName] <String> [-AccountName] <String> [-KeyType] <KeyType>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Set-AzMediaServiceKey** meregenerasi kunci yang digunakan untuk mengakses titik akhir Representational State Transfer (REST) yang terkait dengan layanan media.

## CONTOH

### Contoh 1: Meregenerasi kunci utama yang digunakan untuk mengakses Layanan Media
```
PS C:\>Set-AzMediaServiceKey -ResourceGroupName "ResourceGroup004" -AccountName "MediaService001" -KeyType Primary
```

Perintah ini meregenerasi kunci utama untuk layanan media yang bernama MediaService001 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup004.

### Contoh 2: Meregenerasi kunci sekunder yang digunakan untuk mengakses Layanan Media
```
PS C:\>Set-AzMediaServiceKey -ResourceGroupName "Resourcegroup123" -AccountName "MediaService002" -KeyType Secondary
```

Perintah ini meregenerasi kunci sekunder untuk layanan media bernama MediaService002 yang dimiliki oleh grup sumber daya yang bernama Resourcegroup123.

## PARAMETERS

### -Nama Akun
Menentukan nama layanan media yang digenerasi cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name, ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -KeyType
Menentukan tipe kunci layanan media.
Nilai yang dapat diterima untuk parameter ini adalah: Utama atau Sekunder.

```yaml
Type: Microsoft.Azure.Management.Media.Models.KeyType
Parameter Sets: (All)
Aliases:
Accepted values: Primary, Secondary

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi layanan media.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Media.Models.PSServiceKey

## CATATAN

## LINK TERKAIT

[Get-AzMediaServiceKey](./Get-AzMediaServiceKey.md)


