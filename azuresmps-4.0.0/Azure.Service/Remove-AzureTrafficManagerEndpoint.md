---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: 50B83AEC-1B32-4089-9804-D388677C3F7E
online version: ''
schema: 2.0.0
ms.openlocfilehash: 5b8e09f8547710607935496f0bc543012e9d1ce3
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423199"
---
# Remove-AzureTrafficManagerEndpoint

## SYNOPSIS
Menghapus titik akhir dari Traffic Manager profil.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureTrafficManagerEndpoint -DomainName <String> [-Force]
 -TrafficManagerProfile <IProfileWithDefinition> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureTrafficManagerEndpoint** menghapus titik akhir dari Microsoft Azure Traffic Manager profil.
Setelah Anda menghapus titik akhir, kirim hasilnya ke cmdlet **Set-AzureTrafficManagerProfile** dengan menggunakan operator pipeline.
Cmdlet tersebut tersambung ke Azure untuk menyimpan perubahan Anda.

## EXAMPLES

### Contoh 1: Menghapus titik akhir dari profil
```
PS C:\>$TrafficManagerProfile = Get-AzureTrafficManagerProfile -Name "ContosoProfile"
PS C:\> Remove-AzureTrafficManagerEndpoint -TrafficManagerProfile $TrafficManagerProfile -DomainName "Contoso02App.cloudapp.net" | Set-AzureTrafficManagerProfile
```

Perintah pertama menggunakan cmdlet **Get-AzureTrafficManagerProfile** untuk mendapatkan profil bernama ContosoProfile, lalu menyimpannya di variabel $TrafficManagerProfile tertentu.

Perintah kedua menghapus titik akhir yang memiliki nama domain Contoso02App.cloudapp.net dari profil Traffic Manager yang disimpan di $TrafficManagerProfile.
Perintah melewati objek profil ke cmdlet **Set-AzureTrafficManagerProfile** agar tersambung ke Azure untuk menyimpan perubahan Anda.

## PARAMETERS

### -DomainName
Menentukan nama domain titik akhir yang akan dihapus.

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

### -Force
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

### -TrafficManagerProfile
Menentukan Traffic Manager profil pengguna untuk menghapus titik akhir.

```yaml
Type: IProfileWithDefinition
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.TrafficManager.Models.IProfileWithDefinition
Cmdlet ini menghasilkan objek Traffic Manager profil baru, yang berisi informasi tentang profil yang diperbarui.

## CATATAN

## RELATED LINKS

[Add-AzureTrafficManagerEndpoint](./Add-AzureTrafficManagerEndpoint.md)

[Set-AzureTrafficManagerEndpoint](./Set-AzureTrafficManagerEndpoint.md)

[Get-AzureTrafficManagerProfile](./Get-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](./Set-AzureTrafficManagerProfile.md)


