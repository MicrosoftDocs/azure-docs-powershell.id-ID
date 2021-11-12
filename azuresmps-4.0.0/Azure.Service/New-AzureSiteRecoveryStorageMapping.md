---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 2D09422F-82B1-4243-B835-8BF223A6F936
online version: ''
schema: 2.0.0
ms.openlocfilehash: 59f5173b3f2622ad70f4cc271772d24a85f113f80dfde33db7b2b251d99b74c7
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419215"
---
# New-AzureSiteRecoveryStorageMapping

## SYNOPSIS
Membuat pemetaan antara objek Azure Storage dan pemulihan Storage Anda.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureSiteRecoveryStorageMapping -PrimaryStorage <ASRStorage> -RecoveryStorage <ASRStorage>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureSiteRecoveryStorageMapping** membuat pemetaan antara objek sumber daya Azure Storage utama yang dikelola AzureSiteRecoveryStorageMapping membuat pemetaan antara objek Azure Storage utama yang dikelola Storage pemulihan.

## EXAMPLES

### Contoh 1: Membuat pemetaan antara objek penyimpanan dan objek penyimpanan pemulihan
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> $Storages = Get-AzureSiteRecoveryStorage -Server $Servers[0]
PS C:\> New-AzureSiteRecoveryStorageMapping -PrimaryStorage $Storages[0] -RecoveryStorage $Storages[1]
```

Cmdlet perintah pertama mendapatkan server untuk penyimpanan Pemulihan Situs Azure saat ini menggunakan cmdlet **Get-AzureSiteRecoveryServer.**
Perintah menyimpan server Pemulihan Situs di $Servers array terpisah.

Perintah kedua mendapatkan penyimpanan pemulihan situs untuk server pertama dalam larik $Servers, lalu menyimpannya di $Storages.

Perintah terakhir membuat pemetaan antara jaringan utama dan jaringan pemulihan.
Perintah menentukan objek utama Storage sebagai elemen pertama dalam $Storages.
Perintah menentukan objek Storage pemulihan sebagai elemen kedua dari $Storages.

## PARAMETERS

### -PrimaryStorage
Menentukan metode Storage di peta pemulihan untuk Storage.
Untuk mendapatkan objek **ASRStorage,** gunakan cmdlet Get-AzureSiteRecoveryStorage.

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

### -RecoveryStorage
Menentukan objek pemulihan Storage Anda.
Cmdlet ini memetakan objek Storage utama ke objek Storage yang ditentukan parameter ini.
Untuk mendapatkan objek **ASRStorage,** gunakan **Get-AzureSiteRecoveryStorage**.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSiteRecoveryStorage](./Get-AzureSiteRecoveryStorage.md)

[Get-AzureSiteRecoveryStorageMapping](./Get-AzureSiteRecoveryStorageMapping.md)

[Remove-AzureSiteRecoveryStorageMapping](./Remove-AzureSiteRecoveryStorageMapping.md)


