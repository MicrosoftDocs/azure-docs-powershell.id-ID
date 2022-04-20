---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: F6C01C25-655C-4798-9826-F7CB168181C7
online version: ''
schema: 2.0.0
ms.openlocfilehash: 3647254b7fc56f65efe4587c0a8710aadcf99a3d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142656483"
---
# Get-AzureSiteRecoveryNetworkMapping

## SYNOPSIS
Mendapatkan pemetaan jaringan untuk kubah Site Recovery.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### EnterpriseToEnterprise
```
Get-AzureSiteRecoveryNetworkMapping -PrimaryServer <ASRServer> -RecoveryServer <ASRServer>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### EnterpriseToAzure
```
Get-AzureSiteRecoveryNetworkMapping -PrimaryServer <ASRServer> [-Azure] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSiteRecoveryNetworkMapping** mendapatkan informasi tentang pemetaan jaringan Azure Site Recovery untuk kubah Site Recovery saat ini.

## EXAMPLES

### Contoh 1: Dapatkan pemetaan antara jaringan dan jaringan pemulihan
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> Get-AzureSiteRecoveryNetworkMapping -PrimaryServer $Servers[0] -RecoveryServer $Servers[0]
PrimaryServerId     : 774859b0-1966-48cc-9df7-759c441b7a8c
PrimaryNetworkId    : 7cfd636e-5cc2-4e01-873b-8a7aa4962341
PrimaryNetworkName  : phase2RecoveryVMNetwork
RecoveryServerId    : 774859b0-1966-48cc-9df7-759c441b7a8c
RecoveryNetworkId   : d903e2c6-3141-4cef-bfe1-04616cd43cbb
RecoveryNetworkName : phase2PrimaryVMNetwork
PairingStatus       : OK
```

Cmdlet perintah pertama mendapatkan server untuk brankas Azure Site Recovery saat ini menggunakan cmdlet **Get-AzureSiteRecoveryServer**.
Perintah menyimpan server Site Recovery dalam variabel array $Servers.

Perintah kedua mendapatkan pemetaan antara jaringan utama dan jaringan pemulihan.
Perintah menentukan server utama untuk pemetaan jaringan sebagai elemen pertama $Servers.
Perintah menentukan server untuk jaringan pemulihan sebagai elemen kedua $Servers.

### Contoh 2: Dapatkan pemetaan antara jaringan dan jaringan mesin virtual Azure
```
PS C:\> $Servers = Get-AzureSiteRecoveryServer
PS C:\> Get-AzureSiteRecoveryNetworkMapping -Azure -PrimaryServer $Servers[0] 
PrimaryServerId     : 774859b0-1966-48cc-9df7-759c441b7a8c
PrimaryNetworkId    : 7cfd636e-5cc2-4e01-873b-8a7aa4962341
PrimaryNetworkName  : phase2RecoveryVMNetwork
RecoveryServerId    : 21a9403c-6ec1-44f2-b744-b4e50b792387
RecoveryNetworkId   : ecb3a462-664f-4f57-873e-d09b5925e1a1
RecoveryNetworkName : AzureVMNetwork
PairingStatus       : OK
```

Cmdlet perintah pertama mendapatkan server untuk kubah Site Recovery saat ini.
Perintah menyimpan server dalam variabel array $Servers.

Perintah kedua mendapatkan pemetaan antara jaringan utama dan jaringan mesin virtual Azure.
Perintah menentukan server utama untuk jaringan sebagai elemen pertama $Servers.
Perintah menentukan parameter *Azure* .
Oleh karena itu, perintah mendapatkan pemetaan ke jaringan mesin virtual Azure.

## PARAMETERS

### -Azure
Menunjukkan bahwa cmdlet ini mendapatkan pemetaan jaringan untuk jaringan di server utama yang dipetakan ke jaringan virtual Azure.

```yaml
Type: SwitchParameter
Parameter Sets: EnterpriseToAzure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryServer
Menentukan server utama untuk mendapatkan pemetaan.

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

### -RecoveryServer
Menentukan server pemulihan untuk mendapatkan pemetaan.

```yaml
Type: ASRServer
Parameter Sets: EnterpriseToEnterprise
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

[Baru-AzureSiteRecoveryNetworkMapping](./New-AzureSiteRecoveryNetworkMapping.md)

[Hapus-AzureSiteRecoveryNetworkMapping](./Remove-AzureSiteRecoveryNetworkMapping.md)


