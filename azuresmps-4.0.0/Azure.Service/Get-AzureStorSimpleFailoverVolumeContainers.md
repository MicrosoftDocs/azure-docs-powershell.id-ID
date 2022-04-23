---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: BABBA19E-5833-452C-9E36-811EAE7C20F9
online version: ''
schema: 2.0.0
ms.openlocfilehash: 093d3be147b19a0f3bf5ec6bfbe13affad1b56b4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143043659"
---
# Get-AzureStorSimpleFailoverVolumeContainers

## SYNOPSIS
Mendapatkan grup wadah volume untuk failover perangkat.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### IdentifikasiById
```
Get-AzureStorSimpleFailoverVolumeContainers -DeviceId <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### IdentifikasiByName
```
Get-AzureStorSimpleFailoverVolumeContainers -DeviceName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorSimpleFailoverVolumeContainers** mendapatkan grup wadah volume untuk failover perangkat.
Loloskan grup **VolumeContainer** tunggal atau larik grup **VolumeContainer** ke cmdlet **Start-AzureStorSimpleDeviceFailover** .
Hanya grup yang memiliki nilai $True untuk properti **IsDCGroupEligibleForDR** yang memenuhi syarat untuk failover.

## EXAMPLES

### Contoh 1: Dapatkan kontainer volume failover
```
PS C:\>Get-AzureStorSimpleFailoverVolumeContainers -DeviceName "ChewD_App7"

DCGroup                    IneligibilityMessage          IsDCGroupEligibleForDR
-------                    --------------------          ----------------------
{VolumeContainer1889078...                                                 True
{VC_01}                    No cloud snapshot found                        False
{VolumeContainer7306959}   No cloud snapshot found                        False
{VolumeContainer407850151} No cloud snapshot found                        False
```

Perintah ini mendapatkan kontainer volume failover.
Hanya DCGroup yang memiliki nilai $True untuk properti **IsDCGroupEligibleForDR** yang dapat digunakan untuk failover perangkat.

## PARAMETERS

### -DeviceId
Menentukan ID instans perangkat StorSimple tempat menjalankan cmdlet.

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
Menentukan nama perangkat StorSimple tempat menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IList\<DataContainerGroup\>
Cmdlet ini mengembalikan daftar grup **VolumeContainer** .

## NOTES

## RELATED LINKS

[Start-AzureStorSimpleDeviceFailoverJob](./Start-AzureStorSimpleDeviceFailoverJob.md)

[Get-AzureStorSimpleDeviceVolumeContainer](./Get-AzureStorSimpleDeviceVolumeContainer.md)


