---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 00B8AB6D-02E0-45B5-AB69-49FC69246A34
online version: ''
schema: 2.0.0
ms.openlocfilehash: 456bae3f93e859581aa56930bee06e3d3be3a112
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143104967"
---
# Get-AzureSiteRecoveryRecoveryPlanFile

## SYNOPSIS
Mengunduh paket Site Recovery Azure dalam format XML.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByRPObject (Default)
```
Get-AzureSiteRecoveryRecoveryPlanFile -Path <String> -RecoveryPlan <ASRRecoveryPlan>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ById
```
Get-AzureSiteRecoveryRecoveryPlanFile -Path <String> -Id <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSiteRecoveryRecoveryPlanFile** mengunduh paket Site Recovery Azure dalam format XML.
Anda bisa menggunakan file ini untuk memperbarui rencana pemulihan lalu mengunggahnya ke server Site Recovery.

Rencana pemulihan mengumpulkan mesin virtual dalam grup untuk tujuan failover dan pemulihan.

## EXAMPLES

### Contoh 1: Dapatkan file paket pemulihan
```
PS C:\> $RecoveryPlan = Get-AzureSiteRecoveryRecoveryPlan 
PS C:\> Get-AzureSiteRecoveryRecoveryPlanFile -RecoveryPlan $RecoveryPlan -Path "C:\Users\Contoso\Desktop\RecoveryPlan.xml"
```

Perintah ini menggunakan cmdlet **Get-AzureSiteRecoveryRecoveryPlan** untuk mendapatkan rencana pemulihan, lalu menyimpannya dalam variabel $RecoveryPlan.

Perintah kedua menggunakan cmdlet **GetAzureSiteRecoveryRecoveryPlanFile** untuk mendapatkan file XML rencana pemulihan situs di $RecoveryPlan.
Perintah menyimpan file XML di jalur yang ditentukan.

## PARAMETERS

### -Id
Menentukan ID rencana pemulihan yang akan didapatkan.

```yaml
Type: String
Parameter Sets: ById
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jalur
Menentukan jalur lengkap untuk menyimpan file XML rencana pemulihan.

```yaml
Type: String
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

### -RecoveryPlan
Menentukan objek **ASRRecoveryPlan** untuk mendapatkan rencana pemulihan.
Untuk mendapatkan objek **ASRRecoveryPlan** , gunakan cmdlet **Get-AzureSiteRecoveryPlan** .

```yaml
Type: ASRRecoveryPlan
Parameter Sets: ByRPObject
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

[Get-AzureSiteRecoveryRecoveryPlan](./Get-AzureSiteRecoveryRecoveryPlan.md)


