---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 86438393-8D5A-46A0-B467-6A4434E18011
online version: ''
schema: 2.0.0
ms.openlocfilehash: af42c1b7ce4dea8fc92f35eddd44ed97eeac987a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142981379"
---
# Get-AzureService

## SYNOPSIS
Mengembalikan objek dengan informasi tentang layanan awan untuk langganan saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

[!INCLUDE [rdfe-deprecation-banner](../../includes/rdfe-deprecation-banner.md)]

## SYNTAX

```
Get-AzureService [[-ServiceName] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureService** mengembalikan objek daftar dengan semua layanan cloud Azure yang terkait dengan langganan saat ini.
Jika Anda menentukan parameter *ServiceName* , **Get-AzureService** mengembalikan informasi hanya pada layanan yang cocok.

## EXAMPLES

### Contoh 1: Dapatkan informasi tentang semua layanan
```
PS C:\> Get-AzureService
```

Perintah ini mengembalikan objek yang berisi informasi tentang semua layanan Azure yang terkait dengan langganan saat ini.

### Contoh 2: Dapatkan informasi tentang layanan tertentu
```
PS C:\> Get-AzureService -ServiceName $MySvc
```

Perintah ini mengembalikan informasi tentang layanan $MySvc.

### Contoh 3: Menampilkan metode dan properti yang tersedia
```
PS C:\> Get-AzureService | Get-Member
```

Perintah ini menampilkan properti dan metode yang tersedia dari cmdlet **Get-AzureService** .

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

### -ServiceName
Menentukan nama layanan untuk mengembalikan informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### HostedServiceContext

## NOTES

## RELATED LINKS

[AzureService baru](./New-AzureService.md)

[Set-AzureService](./Set-AzureService.md)


