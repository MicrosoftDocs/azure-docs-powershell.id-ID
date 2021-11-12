---
external help file: Microsoft.Azure.Commands.RecoveryServicesRdfe.dll-Help.xml
ms.assetid: 00B8AB6D-02E0-45B5-AB69-49FC69246A34
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1736d5148f59380a4e72672f91291cc324439a59a9cd1c98d4d2eac69bbded1b
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418653"
---
# Get-AzureSiteRecoveryRecoveryPlanFile

## SYNOPSIS
Mengunduh paket Pemulihan Situs Azure dalam format XML.

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
Cmdlet **Get-AzureSiteRecoveryRecoveryPlanFile** mengunduh paket Pemulihan Situs Azure dalam format XML.
Anda dapat menggunakan file ini untuk memperbarui rencana pemulihan lalu mengunggahnya ke server Pemulihan Situs.

Rencana pemulihan mengumpulkan mesin virtual dalam grup untuk tujuan failover dan pemulihan.

## EXAMPLES

### Contoh 1: Dapatkan file rencana pemulihan
```
PS C:\> $RecoveryPlan = Get-AzureSiteRecoveryRecoveryPlan 
PS C:\> Get-AzureSiteRecoveryRecoveryPlanFile -RecoveryPlan $RecoveryPlan -Path "C:\Users\Contoso\Desktop\RecoveryPlan.xml"
```

Perintah ini menggunakan cmdlet **Get-AzureSiteRecoveryRecoveryPlan** untuk mendapatkan paket pemulihan, lalu menyimpannya di $RecoveryPlan pemulihan.

Perintah kedua menggunakan cmdlet **GetAzureSiteRecoveryRecoveryPlanFile** untuk mendapatkan file XML rencana pemulihan situs $RecoveryPlan.
Perintah menyimpan file XML pada jalur yang ditentukan.

## PARAMETERS

### -Id
Menentukan ID paket pemulihan untuk mendapatkannya.

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

### -Path
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

### -RecoveryPlan
Menentukan objek **ASRRecoveryPlan** untuk mendapatkan rencana pemulihan.
Untuk mendapatkan objek **ASRRecoveryPlan,** gunakan cmdlet **Get-AzureSiteRecoveryRecoveryPlan.**

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSiteRecoveryRecoveryPlan](./Get-AzureSiteRecoveryRecoveryPlan.md)


