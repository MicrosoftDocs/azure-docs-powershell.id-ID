---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: A2CBF963-1FAE-41B0-964E-EFF52076AB32
online version: ''
schema: 2.0.0
ms.openlocfilehash: 996f97eaaad3da5e94ba0d1a917e484af8c3c799
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142981217"
---
# Get-AzureWebsiteJobHistory

## SYNOPSIS
Mendapatkan riwayat pekerjaan web.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### HistoryParameterSetName
```
Get-AzureWebsiteJobHistory -JobName <String> [-Name <String>] [-Slot <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### RunIdParameterSetName
```
Get-AzureWebsiteJobHistory -JobName <String> -RunId <String> [-Name <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### LatestParameterSetName
```
Get-AzureWebsiteJobHistory -JobName <String> [-Latest] [-Name <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan riwayat pekerjaan web.

## EXAMPLES

### Contoh 1: Dapatkan riwayat lengkap untuk pekerjaan web
```
PS C:\> Get-AzureWebsiteJobHistory -Name MyWebsite -JobName MyWebJob
```

Mendapatkan riwayat lengkap untuk MyWebJob.

### Contoh 2: Dapatkan jalankan terbaru untuk pekerjaan web
```
PS C:\> Get-AzureWebsiteJobHistory -Name MyWebsite -JobName MyWebJob -Latest
```

Dapatkan info terbaru untuk MyWebJob.

### Contoh 3: Dapatkan pekerjaan web tertentu
```
PS C:\> Get-AzureWebsiteJobHistory -Name MyWebsite -JobName MyWebJob -RunId 10
```

Dapatkan semua info tentang menjalankan dengan id 10 untuk MyWebJob.

## PARAMETERS

### -JobName
Nama pekerjaan web.

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

### -Terbaru
Jika ditentukan, kembalikan riwayat proses terbaru.

```yaml
Type: SwitchParameter
Parameter Sets: LatestParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama situs web Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -RunId
Menentukan ID riwayat jalankan yang ingin Anda lihat.

```yaml
Type: String
Parameter Sets: RunIdParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Nama slot situs web Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Dapatkan-AzureWebsite](./Get-AzureWebsite.md)

[Baru-AzureSitus Web](./New-AzureWebsite.md)

[Get-AzureWebsiteJob](./Get-AzureWebsiteJob.md)

[AzureWebsiteJob Baru](./New-AzureWebsiteJob.md)

[Hapus-AzureWebsiteJob](./Remove-AzureWebsiteJob.md)


