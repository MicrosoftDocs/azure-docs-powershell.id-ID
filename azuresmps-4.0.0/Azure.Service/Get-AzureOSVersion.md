---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: FAB5E55D-95FC-4545-8BA6-EEFCFDB04200
online version: ''
schema: 2.0.0
ms.openlocfilehash: 8d60bf375381fbe1e21fa4d5eb0b77946f2ae62e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142981667"
---
# Get-AzureOSVersion

## SYNOPSIS
Mencantumkan semua sistem operasi tamu Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureOSVersion [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureOSVersion** mencantumkan semua sistem operasi tamu Azure yang tersedia.

## EXAMPLES

### Contoh 1: Dapatkan semua sistem operasi yang tersedia
```
PS C:\> Get-AzureOSVersion
```

Perintah ini mengambil objek yang berisi daftar semua versi sistem operasi tamu yang tersedia dalam langganan saat ini.

### Contoh 2: Menampilkan informasi sistem operasi dalam tabel
```
PS C:\> Get-AzureOSVersion | Format-Table -AutoSize -Property "Family", "FamilyLabel", "Version"
```

Perintah ini mengambil objek yang berisi daftar semua versi sistem operasi tamu yang tersedia dalam langganan saat ini.
Perintah akan meneruskannya ke cmdlet **Format-Tabel** menggunakan operator pipeline.
Cmdlet tersebut memformatnya sebagai tabel yang memperlihatkan keluarga sistem operasi, label keluarga sistem operasi, dan versi.

## PARAMETERS

### -InformationAction
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureOSDisk](./Get-AzureOSDisk.md)


