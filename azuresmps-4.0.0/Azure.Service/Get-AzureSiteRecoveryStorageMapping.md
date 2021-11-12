---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 4F083EBC-7D7E-4836-8AAB-6BF2B08162DF
online version: ''
schema: 2.0.0
ms.openlocfilehash: e68b42b310c08eb82a63da5bf50b1d8b9c3f592d
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423241"
---
# Get-AzureSiteRecoveryStorageMapping

## SYNOPSIS
Mendapatkan pemetaan objek Storage Pemulihan Situs untuk vault.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureSiteRecoveryStorageMapping -PrimaryServer <ASRServer> -RecoveryServer <ASRServer>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSiteRecoveryStorageMapping** mendapatkan pemetaan objek Pemulihan Situs Azure Storage untuk vault Pemulihan Situs Azure saat ini.

## EXAMPLES

### Contoh 1: Dapatkan pemetaan antara objek Storage dan pemulihan objek Storage Anda
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> Get-AzureSiteRecoveryStorageMapping -PrimaryServer $Servers[0] -RecoveryServer $Servers[1]
PrimaryServerId     : 774859b0-1966-48cc-9df7-759c441b7a8c
PrimaryStorageId    : 1c1d0c0b-0c50-4675-af1a-1fdac70dbb6d
PrimaryStorageName  : phase2PrimaryStorageClassification
RecoveryServerId    : 774859b0-1966-48cc-9df7-759c441b7a8c
RecoveryStorageId   : 20cf8d92-fd5d-4872-985a-0f4562b8a0bf
RecoveryStorageName : phase2RecoveryStorageClassification
```

Cmdlet perintah pertama mendapatkan server untuk penyimpanan Pemulihan Situs Azure saat ini menggunakan cmdlet **Get-AzureSiteRecoveryServer.**
Perintah menyimpan server Pemulihan Situs di $Servers array terpisah.

Perintah kedua memetakan di antara dua Azure Storage objek.
Perintah menentukan server utama untuk pemetaan objek Storage sebagai elemen pertama $Servers.
Perintah menentukan server untuk pemulihan Storage objek sebagai elemen kedua dari $Servers.

## PARAMETERS

### -PrimaryServer
Menentukan server utama.
Untuk mendapatkan server, gunakan cmdlet **Get-AzureSiteRecoveryServer.**

```yaml
Type: ASRServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -RecoveryServer
Menentukan server pemulihan.
Untuk mendapatkan server, gunakan **Get-AzureSiteRecoveryServer**.

```yaml
Type: ASRServer
Parameter Sets: (All)
Aliases: 

Required: True
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

[Get-AzureSiteRecoveryServer](./Get-AzureSiteRecoveryServer.md)

[New-AzureSiteRecoveryStorageMapping](./New-AzureSiteRecoveryStorageMapping.md)

[Remove-AzureSiteRecoveryStorageMapping](./Remove-AzureSiteRecoveryStorageMapping.md)


