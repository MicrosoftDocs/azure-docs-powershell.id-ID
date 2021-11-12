---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: 51A1B699-03F6-4BB9-9186-FDFFB094F16A
online version: ''
schema: 2.0.0
ms.openlocfilehash: d2109f6bb784e574b8ecbfa1914b7afe224ff12e19318621269efff832d3c78d
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419313"
---
# Enable-AzureTrafficManagerProfile

## SYNOPSIS
Mengaktifkan profil Traffic Manager.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Enable-AzureTrafficManagerProfile -Name <String> [-PassThru] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Enable-AzureTrafficManagerProfile** mengaktifkan Microsoft Azure Traffic Manager profil.
Tentukan parameter *PassThru* untuk menampilkan apakah operasi berhasil.

## EXAMPLES

### Contoh 1: Mengaktifkan Traffic Manager profil
```
PS C:\>Enable-AzureTrafficManagerProfile -Name "MyProfile"
```

Perintah ini mengaktifkan profil Traffic Manager bernama MyProfile.

### Contoh 2: Mengaktifkan Traffic Manager profil dan menampilkan hasilnya
```
PS C:\>Enable-AzureTrafficManagerProfile -Name "MyProfile" -PassThru
True
```

Perintah ini memungkinkan Traffic Manager bernama MyProfile dan menampilkan apakah perintah berhasil.

## PARAMETERS

### -Nama
Menentukan nama profil Traffic Manager diaktifkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan $True jika operasi berhasil; jika tidak, $False.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

### System.Boolean
Cmdlet ini menghasilkan $True atau $False.
Jika operasi berhasil dan jika Anda menentukan parameter *PassThru,* cmdlet ini akan mengembalikan nilai $True.

## CATATAN

## RELATED LINKS

[Disable-AzureTrafficManagerProfile](./Disable-AzureTrafficManagerProfile.md)

[Get-AzureTrafficManagerProfile](./Get-AzureTrafficManagerProfile.md)

[New-AzureTrafficManagerProfile](./New-AzureTrafficManagerProfile.md)

[Remove-AzureTrafficManagerProfile](./Remove-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](./Set-AzureTrafficManagerProfile.md)


