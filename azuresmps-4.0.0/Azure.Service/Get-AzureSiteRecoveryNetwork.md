---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 615D2C5D-AB31-45DB-9535-9B9C8E957322
online version: ''
schema: 2.0.0
ms.openlocfilehash: f81b57a585521150745c76b44c8947906c781c8a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424132"
---
# Get-AzureSiteRecoveryNetwork

## SYNOPSIS
Mendapatkan informasi tentang jaringan yang dikelola oleh Pemulihan Situs untuk vault saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureSiteRecoveryNetwork -Server <ASRServer> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSiteRecoveryNetwork** mendapatkan informasi tentang jaringan Pemulihan Situs Azure untuk vault Pemulihan Situs saat ini.

## EXAMPLES

### Contoh 1: Dapatkan jaringan pemulihan situs
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> Get-AzureSiteRecoveryNetwork -Server $Servers[0]
Name                : phase2RecoveryVMNetwork
ID                  : 7cfd636e-5cc2-4e01-873b-8a7aa4962341
FabricObjectID      : 7cfd636e-5cc2-4e01-873b-8a7aa4962341
ServerId            : 774859b0-1966-48cc-9df7-759c441b7a8c
Type                : NoIsolation
FabricType          : VMM
VmNetworkSubnetList : {}

Name                : phase2PrimaryVMNetwork
ID                  : d903e2c6-3141-4cef-bfe1-04616cd43cbb
FabricObjectID      : d903e2c6-3141-4cef-bfe1-04616cd43cbb
ServerId            : 774859b0-1966-48cc-9df7-759c441b7a8c
Type                : NoIsolation
FabricType          : VMM
VmNetworkSubnetList : {}
```

Cmdlet perintah pertama mendapatkan server untuk penyimpanan Pemulihan Situs Azure saat ini menggunakan cmdlet **Get-AzureSiteRecoveryServer.**
Perintah menyimpan server Pemulihan Situs di $Servers array terpisah.

Perintah kedua mendapatkan jaringan pemulihan situs untuk server pertama dalam $Servers larik.

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

### -Server
Menentukan server Pemulihan Situs.

```yaml
Type: ASRServer
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




