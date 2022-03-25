---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: BB36A434-6BE3-46BF-B10A-FCD6C766CB84
online version: ''
schema: 2.0.0
ms.openlocfilehash: 2bf6c89569fdd5ce9710736bfd023d677b676fbf
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/24/2022
ms.locfileid: "132414781"
---
# Remove-AzureSiteRecoveryNetworkMapping

## SYNOPSIS
Menghapus pemetaan jaringan dari vault Pemulihan Situs.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureSiteRecoveryNetworkMapping -NetworkMapping <ASRNetworkMapping> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureSiteRecoveryNetworkMapping** menghapus pemetaan jaringan dari vault Pemulihan Situs Azure saat ini.

## EXAMPLES

### Contoh 1: Hapus pemetaan antara jaringan dan jaringan pemulihan
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> $NetworkMapping = Get-AzureSiteRecoveryNetworkMapping -PrimaryServer $Servers[0] -RecoveryServer $Servers[0]
PS C:\> Remove-AzureSiteRecoveryNetworkMapping -NetworkMapping $NetworkMapping
```

Cmdlet perintah pertama mendapatkan server untuk penyimpanan Pemulihan Situs Azure saat ini menggunakan cmdlet **Get-AzureSiteRecoveryServer** .
Perintah menyimpan server Pemulihan Situs di $Servers array baru.

Perintah kedua mendapatkan pemetaan antara jaringan utama dan jaringan pemulihan, lalu menyimpannya di variabel $NetworkMapping pemulihan.
Perintah menentukan server utama untuk pemetaan jaringan sebagai elemen pertama dalam $Servers.
Perintah menentukan server untuk jaringan pemulihan sebagai elemen kedua dari $Servers.

Perintah terakhir menghapus pemetaan jaringan dalam $NetworkMapping.

### Contoh 2: Menghapus pemetaan antara jaringan dan jaringan mesin virtual Azure
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> $NetworkMapping = Get-AzureSiteRecoveryNetworkMapping -PrimaryServer $Servers[0] -Azure
PS C:\> Remove-AzureSiteRecoveryNetworkMapping -NetworkMapping $NetworkMapping
```

Cmdlet perintah pertama mendapatkan server untuk vault Pemulihan Situs saat ini.
Perintah menyimpan server Pemulihan Situs di $Servers array baru.

Perintah kedua mendapatkan pemetaan antara jaringan utama dan jaringan mesin virtual Azure, lalu menyimpannya dalam $NetworkMapping lokal.
Perintah menentukan server utama untuk jaringan sebagai elemen pertama dalam $Servers.
Perintah menentukan parameter *Azure* .
Oleh karena itu, perintah akan memetakannya ke jaringan mesin virtual Azure.

Perintah terakhir menghapus pemetaan jaringan dalam $NetworkMapping.

## PARAMETERS

### -NetworkMapping
Menentukan pemetaan jaringan yang akan dihapus.

```yaml
Type: ASRNetworkMapping
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSiteRecoveryNetworkMapping](./Get-AzureSiteRecoveryNetworkMapping.md)

[New-AzureSiteRecoveryNetworkMapping](./New-AzureSiteRecoveryNetworkMapping.md)

[Get-AzureSiteRecoveryServer](./Get-AzureSiteRecoveryServer.md)


