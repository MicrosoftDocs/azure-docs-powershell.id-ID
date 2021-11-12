---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 185506BC-6155-4517-BCBD-BCDE7450C7A8
online version: ''
schema: 2.0.0
ms.openlocfilehash: bc9fe4a786c42a4a83efadabb34d905dc86045158351e7ff0645d4cde382cd13
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417687"
---
# Start-AzureSiteRecoveryProtectionProfileDissociationJob

## SYNOPSIS
Memulai pekerjaan disosiasi pada kebijakan replikasi yang terkait dengan wadah proteksi Pemulihan Situs.

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
Cmdlet **Start-AzureSiteRecoveryProtectionProfileDissociationJob** memulai pekerjaan dissociation pada kebijakan replikasi yang terkait dengan wadah proteksi Pemulihan Situs Azure.

## EXAMPLES

### Contoh 1: Dissociate a protection profile
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

Perintah pertama mendapatkan wadah proteksi dengan menggunakan cmdlet **Get-AzureSiteRecoveryProtectionContainer,** lalu menyimpan wadah itu di variabel $ProtectionContainer 01.

Perintah kedua mendapatkan wadah proteksi, lalu menyimpannya di variabel $ProtectionContainer 02.

Perintah terakhirssociate proteksi profil dari wadah yang disimpan $ProtectionContainer 01 sebagai wadah proteksi utama.
Perintah tersebut mengusutkan wadah yang disimpan $ProtectionContainer 02 sebagai wadah proteksi pemulihan.

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

### -ProtectionProfile
Menentukan pengaturan profil proteksi agar terpisah dari wadah proteksi.
Menentukan pengaturan profil proteksi yang akan diterapkan pada wadah proteksi.
Untuk mendapatkan objek **ASRProtectionProfile,** gunakan cmdlet New-AzureSiteRecoveryProtectionProfileObject cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSiteRecoveryProtectionContainer](./Get-AzureSiteRecoveryProtectionContainer.md)

[New-AzureSiteRecoveryProtectionProfileObject](./New-AzureSiteRecoveryProtectionProfileObject.md)

[Start-AzureSiteRecoveryProtectionProfileAssociationJob](./Start-AzureSiteRecoveryProtectionProfileAssociationJob.md)


