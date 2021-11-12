---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: BB36A434-6BE3-46BF-B10A-FCD6C766CB84
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9bc83eab7b731712b8b36a148fb5ffe36df73674ce9525a79bfdfd3220c66666
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
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

Cmdlet perintah pertama mendapatkan server untuk penyimpanan Pemulihan Situs Azure saat ini menggunakan cmdlet **Get-AzureSiteRecoveryServer.**
Perintah menyimpan server Pemulihan Situs di $Servers array terpisah.

Perintah kedua mendapatkan pemetaan antara jaringan utama dan jaringan pemulihan, lalu menyimpannya dalam variabel $NetworkMapping pemulihan.
Perintah menentukan server utama untuk pemetaan jaringan sebagai elemen pertama dalam $Servers.
Perintah menentukan server untuk jaringan pemulihan sebagai elemen kedua dari $Servers.

Perintah terakhir menghapus pemetaan jaringan pada $NetworkMapping.

### Contoh 2: Menghapus pemetaan antara jaringan dan jaringan mesin virtual Azure
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> $NetworkMapping = Get-AzureSiteRecoveryNetworkMapping -PrimaryServer $Servers[0] -Azure
PS C:\> Remove-AzureSiteRecoveryNetworkMapping -NetworkMapping $NetworkMapping
```

Cmdlet perintah pertama mendapatkan server untuk vault Pemulihan Situs saat ini.
Perintah menyimpan server Pemulihan Situs di $Servers array terpisah.

Perintah kedua mendapatkan pemetaan antara jaringan utama dan jaringan mesin virtual Azure, lalu menyimpannya di $NetworkMapping lokal.
Perintah menentukan server utama untuk jaringan sebagai elemen pertama dalam $Servers.
Perintah menentukan parameter *Azure.*
Oleh karena itu, perintah akan memetakannya ke jaringan mesin virtual Azure.

Perintah terakhir menghapus pemetaan jaringan pada $NetworkMapping.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSiteRecoveryNetworkMapping](./Get-AzureSiteRecoveryNetworkMapping.md)

[New-AzureSiteRecoveryNetworkMapping](./New-AzureSiteRecoveryNetworkMapping.md)

[Get-AzureSiteRecoveryServer](./Get-AzureSiteRecoveryServer.md)


