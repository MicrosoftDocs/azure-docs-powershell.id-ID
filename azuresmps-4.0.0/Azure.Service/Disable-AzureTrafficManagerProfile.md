---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: ECE9C2A6-7DA2-4477-B877-9970FBE26D7C
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1f1394b40e0679e1045bfbe3e7e2355fa6ae6412
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141773025"
---
# Disable-AzureTrafficManagerProfile

## SYNOPSIS
Menonaktifkan profil Traffic Manager.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Disable-AzureTrafficManagerProfile -Name <String> [-PassThru] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Disable-AzureTrafficManagerProfile** menonaktifkan profil Microsoft Azure Traffic Manager.
Anda dapat menggunakan parameter *PassThru* untuk menampilkan apakah operasi berhasil.

## EXAMPLES

### Contoh 1: Menonaktifkan profil Traffic Manager dan menampilkan hasilnya
```
PS C:\>Disable-AzureTrafficManagerProfile -Name "MyProfile" -PassThru
True
```

Perintah ini menonaktifkan profil Traffic Manager bernama MyProfile.
Perintah menentukan parameter *PassThru* untuk menampilkan apakah perintah berhasil.

### Contoh 2: Menonaktifkan profil Traffic Manager dan tidak menampilkan hasil
```
PS C:\>Disable-AzureTrafficManagerProfile -Name "MyProfile"
```

Perintah ini menonaktifkan profil Traffic Manager bernama MyProfile tetapi tidak menampilkan apakah perintah berhasil.

## PARAMETERS

### -Nama
Menentukan nama profil Traffic Manager untuk dinonaktifkan.

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

[Enable-AzureTrafficManagerProfile](./Enable-AzureTrafficManagerProfile.md)

[Get-AzureTrafficManagerProfile](./Get-AzureTrafficManagerProfile.md)

[New-AzureTrafficManagerProfile](./New-AzureTrafficManagerProfile.md)

[Hapus-AzureTrafficManagerProfile](./Remove-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](./Set-AzureTrafficManagerProfile.md)


