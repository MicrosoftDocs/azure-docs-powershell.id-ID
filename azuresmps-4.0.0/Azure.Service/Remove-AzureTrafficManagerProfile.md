---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: B96A64DD-9005-4B04-A720-6FCF33797E8D
online version: ''
schema: 2.0.0
ms.openlocfilehash: 33e019a4b1542d307588f9b52203a579e0284960
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142334786"
---
# Remove-AzureTrafficManagerProfile

## SYNOPSIS
Menghapus profil Traffic Manager.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureTrafficManagerProfile -Name <String> [-Force] [-PassThru] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureTrafficManagerProfile** menghapus profil Microsoft Azure Traffic Manager dari langganan saat ini.

## EXAMPLES

### Contoh 1: Menghapus profil Traffic Manager
```
PS C:\>Remove-AzureTrafficManagerProfile -Name "MyProfile"
```

Perintah ini menghapus profil Traffic Manager bernama MyProfile.

### Contoh 2: Menghapus profil Traffic Manager
```
PS C:\>Remove-AzureTrafficManagerProfile -Name "MyProfile" -Force -PassThru
```

Perintah ini menghapus profil Traffic Manager bernama MyProfile tanpa meminta konfirmasi, dan mengembalikan hasilnya.

## PARAMETERS

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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

### -Nama
Menentukan nama profil Traffic Manager untuk dihapus.

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
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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

### System.Boolean
Cmdlet ini menghasilkan $True atau $False.
Jika operasi berhasil dan jika Anda menentukan parameter *PassThru* , cmdlet ini mengembalikan nilai $True.

## CATATAN

## RELATED LINKS

[Nonaktifkan-AzureTrafficManagerProfile](./Disable-AzureTrafficManagerProfile.md)

[Enable-AzureTrafficManagerProfile](./Enable-AzureTrafficManagerProfile.md)

[Get-AzureTrafficManagerProfile](./Get-AzureTrafficManagerProfile.md)

[New-AzureTrafficManagerProfile](./New-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](./Set-AzureTrafficManagerProfile.md)


