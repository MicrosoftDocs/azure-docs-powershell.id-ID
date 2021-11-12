---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: D40937C2-9BF7-4371-A64C-B44F5B6B895E
online version: ''
schema: 2.0.0
ms.openlocfilehash: 27cbb29b66be41057a1d4ad29751fb0530c9b3ac613821beaf3bc3fc60122d3e
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419400"
---
# Get-AzureRemoteAppVM

## SYNOPSIS
Dapatkan mesin virtual dalam koleksi Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRemoteAppVM -CollectionName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRemoteAppVM** mendapatkan mesin virtual yang dibuat di bawah kumpulan Azure RemoteApp untuk hosting sesi.

## EXAMPLES

### Contoh 1: Menampilkan mesin virtual dalam koleksi
```
PS C:\> Get-AzureRemoteAppVM -CollectionName "Contoso"
```

Perintah ini menampilkan mesin virtual yang digunakan untuk sesi hosting dalam koleksi Azure RemoteApp bernama Contoso.

## PARAMETERS

### -CollectionName
Menentukan nama koleksi Azure RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Mulai ulang-AzureRemoteAppVM](./Restart-AzureRemoteAppVM.md)


