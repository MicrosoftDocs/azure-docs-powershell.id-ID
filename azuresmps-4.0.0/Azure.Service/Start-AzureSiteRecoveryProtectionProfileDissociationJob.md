---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 185506BC-6155-4517-BCBD-BCDE7450C7A8
online version: ''
schema: 2.0.0
ms.openlocfilehash: 51485660efc815d1e29c7ba8a23bc89268b3208f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141965939"
---
# Start-AzureSiteRecoveryProtectionProfileDissociationJob

## SYNOPSIS
Memulai pekerjaan disosiasi pada kebijakan replikasi yang terkait dengan wadah perlindungan Site Recovery.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### EnterpriseToAzure (Default)
```
Start-AzureSiteRecoveryProtectionProfileDissociationJob -ProtectionProfile <ASRProtectionProfile>
 -PrimaryProtectionContainer <ASRProtectionContainer> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### EnterpriseToEnterprise
```
Start-AzureSiteRecoveryProtectionProfileDissociationJob -ProtectionProfile <ASRProtectionProfile>
 -PrimaryProtectionContainer <ASRProtectionContainer> -RecoveryProtectionContainer <ASRProtectionContainer>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureSiteRecoveryProtectionProfileDissociationJob** memulai pekerjaan disosiasi pada kebijakan replikasi yang terkait dengan wadah perlindungan azure Site Recovery.

## EXAMPLES

### Contoh 1: Memisahkan profil proteksi
```
PS C:\> $ProtectionContainer01 = Get-AzureSiteRecoveryProtectionContainer -Id "5ba2ea95-856d-4033-9ca3-91e3e2c080b9"
PS C:\> $ProtectionContainer02 = Get-AzureSiteRecoveryProtectionContainer -Id "cf011f2a-aa19-443c-9f60-357f6b8afb77"
PS C:\> Start-AzureSiteRecoveryProtectionProfileDissociationJob -PrimaryProtectionContainer $ProtectionContainer01 -ProtectionProfile $ProtectionContainer01.AvailableProtectionProfiles[0] -RecoveryProtectionContainer $ProtectionContainer02
Name             : MyProtectionProfile
ID               : 51978b0f-9241-4153-9171-2e19344f0805
ClientRequestId  : bb6f3200-b7c6-4c6f-bcbc-a70bb9946f03-2015-01-30 02:55:55Z-P
State            : NotStarted
StateDescription : NotStarted
StartTime        : 
EndTime          : 
AllowedActions   : 
Tasks            : {}
Errors           : {}
```

Perintah pertama mendapatkan wadah perlindungan dengan menggunakan cmdlet **Get-AzureSiteRecoveryProtectionContainer** , lalu menyimpan wadah tersebut dalam variabel $ProtectionContainer 01.

Perintah kedua mendapatkan wadah perlindungan, lalu menyimpannya dalam variabel $ProtectionContainer 02.

Perintah akhir memisahkan profil proteksi dari wadah yang disimpan di $ProtectionContainer 01 sebagai wadah perlindungan utama.
Perintah memisahkan wadah yang disimpan di $ProtectionContainer 02 sebagai wadah perlindungan pemulihan.

## PARAMETERS

### -PrimaryProtectionContainer
Menentukan wadah proteksi utama.

```yaml
Type: ASRProtectionContainer
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

### -ProtectionProfile
Menentukan pengaturan profil proteksi untuk memisahkan diri dari wadah proteksi.
Menentukan pengaturan profil proteksi untuk diterapkan ke wadah proteksi.
Untuk mendapatkan objek **ASRProtectionProfile** , gunakan cmdlet New-AzureSiteRecoveryProtectionProfileObject.

```yaml
Type: ASRProtectionProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryProtectionContainer
Menentukan wadah proteksi pemulihan.

```yaml
Type: ASRProtectionContainer
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

## CATATAN

## RELATED LINKS

[Get-AzureSiteRecoveryProtectionContainer](./Get-AzureSiteRecoveryProtectionContainer.md)

[New-AzureSiteRecoveryProtectionProfileObject](./New-AzureSiteRecoveryProtectionProfileObject.md)

[Start-AzureSiteRecoveryProtectionProfileAssociationJob](./Start-AzureSiteRecoveryProtectionProfileAssociationJob.md)


