---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 2D09422F-82B1-4243-B835-8BF223A6F936
online version: ''
schema: 2.0.0
ms.openlocfilehash: cf545dd76f803f567cce0fa664ae11d3d3031cd0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142723906"
---
# New-AzureSiteRecoveryStorageMapping

## SYNOPSIS
Membuat pemetaan antara objek Azure Storage dan objek Storage pemulihan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureSiteRecoveryStorageMapping -PrimaryStorage <ASRStorage> -RecoveryStorage <ASRStorage>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **AzureSiteRecoveryStorageMapping baru** membuat pemetaan antara objek Azure Storage utama yang dikelola Azure Site Recovery dan objek Storage pemulihan.

## EXAMPLES

### Contoh 1: Membuat pemetaan antara objek penyimpanan dan objek penyimpanan pemulihan
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> $Storages = Get-AzureSiteRecoveryStorage -Server $Servers[0]
PS C:\> New-AzureSiteRecoveryStorageMapping -PrimaryStorage $Storages[0] -RecoveryStorage $Storages[1]
```

Cmdlet perintah pertama mendapatkan server untuk brankas Azure Site Recovery saat ini menggunakan cmdlet **Get-AzureSiteRecoveryServer**.
Perintah menyimpan server Site Recovery dalam variabel array $Servers.

Perintah kedua mendapatkan penyimpanan pemulihan situs untuk server pertama dalam array $Servers, lalu menyimpannya di $Storages.

Perintah akhir membuat pemetaan antara jaringan utama dan jaringan pemulihan.
Perintah menentukan objek Storage utama sebagai elemen pertama $Storages.
Perintah menentukan objek Storage pemulihan sebagai elemen kedua $Storages.

## PARAMETERS

### -PrimaryStorage
Menentukan Storage utama untuk memetakan ke Storage pemulihan.
Untuk mendapatkan objek **ASRStorage** , gunakan cmdlet Get-AzureSiteRecoveryStorage.

```yaml
Type: ASRStorage
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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

### -RecoveryStorage
Menentukan objek Storage pemulihan.
Cmdlet ini memetakan objek Storage utama ke objek Storage yang ditentukan parameter ini.
Untuk mendapatkan objek **ASRStorage** , gunakan **Get-AzureSiteRecoveryStorage**.

```yaml
Type: ASRStorage
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSiteRecoveryStorage](./Get-AzureSiteRecoveryStorage.md)

[Get-AzureSiteRecoveryStorageMapping](./Get-AzureSiteRecoveryStorageMapping.md)

[Hapus-AzureSiteRecoveryStorageMapping](./Remove-AzureSiteRecoveryStorageMapping.md)


