---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: BB36A434-6BE3-46BF-B10A-FCD6C766CB84
online version: ''
schema: 2.0.0
ms.openlocfilehash: 2bf6c89569fdd5ce9710736bfd023d677b676fbf
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142244449"
---
# Remove-AzureSiteRecoveryNetworkMapping

## SYNOPSIS
Menghapus pemetaan jaringan dari kubah Site Recovery.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureSiteRecoveryNetworkMapping -NetworkMapping <ASRNetworkMapping> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureSiteRecoveryNetworkMapping** menghapus pemetaan jaringan dari brankas Azure Site Recovery saat ini.

## EXAMPLES

### Contoh 1: Hapus pemetaan antara jaringan dan jaringan pemulihan
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> $NetworkMapping = Get-AzureSiteRecoveryNetworkMapping -PrimaryServer $Servers[0] -RecoveryServer $Servers[0]
PS C:\> Remove-AzureSiteRecoveryNetworkMapping -NetworkMapping $NetworkMapping
```

Cmdlet perintah pertama mendapatkan server untuk brankas Azure Site Recovery saat ini menggunakan cmdlet **Get-AzureSiteRecoveryServer**.
Perintah menyimpan server Site Recovery dalam variabel array $Servers.

Perintah kedua mendapatkan pemetaan antara jaringan utama dan jaringan pemulihan, lalu menyimpannya dalam variabel $NetworkMapping.
Perintah menentukan server utama untuk pemetaan jaringan sebagai elemen pertama $Servers.
Perintah menentukan server untuk jaringan pemulihan sebagai elemen kedua $Servers.

Perintah akhir menghapus pemetaan jaringan dalam $NetworkMapping.

### Contoh 2: Hapus pemetaan antara jaringan dan jaringan mesin virtual Azure
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> $NetworkMapping = Get-AzureSiteRecoveryNetworkMapping -PrimaryServer $Servers[0] -Azure
PS C:\> Remove-AzureSiteRecoveryNetworkMapping -NetworkMapping $NetworkMapping
```

Cmdlet perintah pertama mendapatkan server untuk kubah Site Recovery saat ini.
Perintah menyimpan server Site Recovery dalam variabel array $Servers.

Perintah kedua mendapatkan pemetaan antara jaringan utama dan jaringan mesin virtual Azure, lalu menyimpannya dalam variabel $NetworkMapping.
Perintah menentukan server utama untuk jaringan sebagai elemen pertama $Servers.
Perintah menentukan parameter *Azure* .
Oleh karena itu, perintah mendapatkan pemetaan ke jaringan mesin virtual Azure.

Perintah akhir menghapus pemetaan jaringan dalam $NetworkMapping.

## PARAMETERS

### -NetworkMapping
Menentukan pemetaan jaringan untuk dihapus.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSiteRecoveryNetworkMapping](./Get-AzureSiteRecoveryNetworkMapping.md)

[Baru-AzureSiteRecoveryNetworkMapping](./New-AzureSiteRecoveryNetworkMapping.md)

[Get-AzureSiteRecoveryServer](./Get-AzureSiteRecoveryServer.md)


