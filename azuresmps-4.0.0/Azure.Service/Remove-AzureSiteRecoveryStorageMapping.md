---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 0A1FD05F-6573-46D8-8217-C7EA432F6742
online version: ''
schema: 2.0.0
ms.openlocfilehash: cd4bb8987331f13910c9f283cfc505d685f4083f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143210519"
---
# Remove-AzureSiteRecoveryStorageMapping

## SYNOPSIS
Menghapus pemetaan objek Storage untuk kubah Site Recovery.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureSiteRecoveryStorageMapping -StorageMapping <ASRStorageMapping> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureSiteRecoveryStorageMapping** menghapus pemetaan objek Storage untuk kubah Azure Site Recovery saat ini.

## EXAMPLES

### Contoh 1: Hapus pemetaan antara jaringan dan jaringan pemulihan
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> $StorageMapping = Get-AzureSiteRecoveryStorageMapping -PrimaryServer $Servers[0] -RecoveryServer $Servers[1]
PS C:\> Remove-AzureSiteRecoveryStorageMapping -StorageMapping $StorageMapping
Get-AzureSiteRecoveryServerGet-AzureSiteRecoveryStorageMappingNew-AzureSiteRecoveryStorageMapping
```

Cmdlet perintah pertama mendapatkan server untuk brankas Azure Site Recovery saat ini menggunakan cmdlet **Get-AzureSiteRecoveryServer**.
Perintah menyimpan server Site Recovery dalam variabel array $Servers.

Perintah kedua mendapatkan pemetaan antara dua objek Storage, lalu menyimpannya dalam variabel $StorageMapping.
Perintah menentukan server utama untuk pemetaan jaringan sebagai elemen pertama $Servers.
Perintah menentukan server untuk jaringan pemulihan sebagai elemen kedua $Servers.

Perintah akhir menghapus pemetaan dalam $StorageMapping.

## PARAMETERS

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

### -StorageMapping
Menentukan pemetaan jaringan.
Untuk mendapatkan **ASRStorageMapping**, gunakan cmdlet **Get-AzureSiteRecoveryStorage** .

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureSiteRecoveryStorage](./Get-AzureSiteRecoveryStorage.md)


