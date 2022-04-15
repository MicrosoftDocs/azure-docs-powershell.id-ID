---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: CFAA371E-F320-4FC3-80E0-5C857E5C0998
online version: ''
schema: 2.0.0
ms.openlocfilehash: ceeafb28e81f1167e836fda6070ef60453303a07
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142278511"
---
# Get-AzureVNetSite

## SYNOPSIS
Mendapatkan objek daftar dengan informasi tentang jaringan virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureVNetSite [[-VNetName] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureVNetSite** mendapatkan objek daftar dengan informasi tentang jaringan virtual Azure untuk langganan saat ini.
Jika Anda menentukan nama jaringan virtual, hanya informasi untuk jaringan virtual tersebut yang dikembalikan.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang semua jaringan virtual dalam langganan saat ini
```
PS C:\> Get-AzureVNetSite
```

Perintah ini mendapatkan informasi tentang semua jaringan virtual dalam langganan saat ini.

### Contoh 2: Dapatkan informasi tentang jaringan virtual tertentu dalam langganan saat ini
```
PS C:\> Get-AzureVNetSite -VNetName "MyProductionNetwork"
```

Perintah ini mengambil informasi hanya di jaringan virtual MyProductionNetwork.

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

### -VNetName
Menentukan nama jaringan virtual untuk mengembalikan informasi tentang.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureVNetConfig](./Get-AzureVNetConfig.md)

[Hapus-AzureVNetConfig](./Remove-AzureVNetConfig.md)

[Set-AzureVNetConfig](./Set-AzureVNetConfig.md)


