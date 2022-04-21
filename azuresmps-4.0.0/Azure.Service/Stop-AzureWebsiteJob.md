---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 7D39F4C9-F37A-4BBE-BF02-1F036A9FC5E8
online version: ''
schema: 2.0.0
ms.openlocfilehash: 6f238ae0238d4707ac16af0d175283e0e592c430
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142786890"
---
# Stop-AzureWebsiteJob

## SYNOPSIS
Menghentikan pekerjaan web untuk situs web.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Stop-AzureWebsiteJob -JobName <String> [-PassThru] [-Name <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Stop-AzureWebsiteJob** menghentikan pekerjaan web untuk situs web.

## EXAMPLES

### Contoh 1: Menghentikan pekerjaan web untuk situs web
```
PS C:\> Stop-AzureWebsiteJob -Name MyWebsite -JobName MyWebJob
```

Menghentikan pekerjaan web bernama MyWebJob for MyWebSite.

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

### -PassThru
Mengembalikan nilai boolean yang mengindikasikan bahwa pekerjaan berhasil dihentikan.
Secara default, cmdlet ini tidak mengembalikan output apa pun.

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

[Berhenti-AzureSitus Web](./Stop-AzureWebsite.md)

[Get-AzureWebsiteJob](./Get-AzureWebsiteJob.md)

[AzureWebsiteJob Baru](./New-AzureWebsiteJob.md)

[Hapus-AzureWebsiteJob](./Remove-AzureWebsiteJob.md)

[Start-AzureWebsiteJob](./Start-AzureWebsiteJob.md)


