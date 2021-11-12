---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: BABBA19E-5833-452C-9E36-811EAE7C20F9
online version: ''
schema: 2.0.0
ms.openlocfilehash: 00e685c1ede0e8ff7b65142fa663d9b860e4e25ac491999829ed56a9e663293c
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418860"
---
# Get-AzureStorSimpleFailoverVolumeContainers

## SYNOPSIS
Mendapatkan grup wadah volume untuk failover perangkat.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### IdentifyById
```
Get-AzureStorSimpleFailoverVolumeContainers -DeviceId <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifyByName
```
Get-AzureStorSimpleFailoverVolumeContainers -DeviceName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorSimpleFailoverVolumeContainers** mendapatkan grup wadah volume untuk failover perangkat.
Akses satu **grup VolumeContainer** atau larik grup **VolumeContainer** ke cmdlet **Start-AzureStorSimpleDeviceFailover.**
Hanya grup yang memiliki nilai $True untuk **properti IsDCGroupEligibleForDR** yang memenuhi syarat untuk failover.

## EXAMPLES

### Contoh 1: Mendapatkan wadah volume failover
```
PS C:\>Get-AzureStorSimpleFailoverVolumeContainers -DeviceName "ChewD_App7"

DCGroup                    IneligibilityMessage          IsDCGroupEligibleForDR
-------                    --------------------          ----------------------
{VolumeContainer1889078...                                                 True
{VC_01}                    No cloud snapshot found                        False
{VolumeContainer7306959}   No cloud snapshot found                        False
{VolumeContainer407850151} No cloud snapshot found                        False
```

Perintah ini mendapatkan wadah volume failover.
Hanya DCGroups yang memiliki nilai $True untuk properti **IsDCGroupEligibleForDR** dapat digunakan untuk failover perangkat.

## PARAMETERS

### -DeviceId
Menentukan ID instans perangkat StorSimple yang digunakan untuk menjalankan cmdlet.

```yaml
Type: String
Parameter Sets: IdentifyById
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeviceName
Menentukan nama perangkat StorSimple yang digunakan untuk menjalankan cmdlet.

```yaml
Type: String
Parameter Sets: IdentifyByName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure.

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

### IList\<DataContainerGroup\>
Cmdlet ini mengembalikan daftar grup **VolumeContainer.**

## CATATAN

## RELATED LINKS

[Start-AzureStorSimpleDeviceFailoverJob](./Start-AzureStorSimpleDeviceFailoverJob.md)

[Get-AzureStorSimpleDeviceVolumeContainer](./Get-AzureStorSimpleDeviceVolumeContainer.md)


