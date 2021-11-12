---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 0A1FD05F-6573-46D8-8217-C7EA432F6742
online version: ''
schema: 2.0.0
ms.openlocfilehash: cd4bb8987331f13910c9f283cfc505d685f4083f
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422064"
---
# Remove-AzureSiteRecoveryStorageMapping

## SYNOPSIS
Menghapus pemetaan Storage pemetaan objek untuk vault Pemulihan Situs.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureSiteRecoveryStorageMapping -StorageMapping <ASRStorageMapping> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureSiteRecoveryStorageMapping** menghapus pemetaan objek Storage untuk vault Pemulihan Situs Azure saat ini.

## EXAMPLES

### Contoh 1: Hapus pemetaan antara jaringan dan jaringan pemulihan
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> $StorageMapping = Get-AzureSiteRecoveryStorageMapping -PrimaryServer $Servers[0] -RecoveryServer $Servers[1]
PS C:\> Remove-AzureSiteRecoveryStorageMapping -StorageMapping $StorageMapping
Get-AzureSiteRecoveryServerGet-AzureSiteRecoveryStorageMappingNew-AzureSiteRecoveryStorageMapping
```

Cmdlet perintah pertama mendapatkan server untuk penyimpanan Pemulihan Situs Azure saat ini menggunakan cmdlet **Get-AzureSiteRecoveryServer.**
Perintah menyimpan server Pemulihan Situs di $Servers array terpisah.

Perintah kedua memetakan antara dua Storage baru, lalu menyimpannya di $StorageMapping variabel.
Perintah menentukan server utama untuk pemetaan jaringan sebagai elemen pertama dalam $Servers.
Perintah menentukan server untuk jaringan pemulihan sebagai elemen kedua dari $Servers.

Perintah terakhir menghapus pemetaan pada $StorageMapping.

## PARAMETERS

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

### -StorageMapping
Menentukan pemetaan jaringan.
Untuk mendapatkan **ASRStorageMapping,** gunakan cmdlet **Get-AzureSiteRecoveryStorage.**

```yaml
Type: ASRStorageMapping
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSiteRecoveryStorage](./Get-AzureSiteRecoveryStorage.md)


