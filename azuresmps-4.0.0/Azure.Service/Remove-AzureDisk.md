---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 75A50C59-28D1-4D29-A420-D24BF479F79E
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1dd6da9a2bd726552600a67572abed7a8438bdd3
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425079"
---
# Remove-AzureDisk

## SYNOPSIS
Menghapus disk dari penyimpanan disk Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureDisk [-DiskName] <String> [-DeleteVHD] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureDisk** menghapus disk dari penyimpanan disk Azure di langganan saat ini.
Secara default, cmdlet ini tidak menghapus file hard disk virtual (VHD) dari penyimpanan blob.
Untuk menghapus VHD, tentukan parameter *DeleteVHD.*

## EXAMPLES

### Contoh 1: Hapus disk
```
PS C:\> Remove-AzureDisk -DiskName "ContosoDataDisk"
```

Perintah ini menghapus disk bernama disk ContosoDataDisk dari penyimpanan disk.
Perintah tidak menghapus VHD.

### Contoh 2: Menghapus disk
```
PS C:\> Remove-AzureDisk -DiskName "ContosoDataDisk" -DeleteVHD
```

Perintah ini menghapus disk bernama disk ContosoDataDisk dari penyimpanan disk.
Perintah ini menentukan parameter DeleteVHD.
Oleh karena itu, perintah akan menghapus VHD dari Azure Storage.

## PARAMETERS

### -DeleteVHD
Menunjukkan bahwa cmdlet ini menghapus VHD dari penyimpanan blob.

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

### -DiskName
Menentukan nama disk data di penyimpanan disk yang dihapus cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

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
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

## CATATAN

## RELATED LINKS

[Add-AzureDisk](./Add-AzureDisk.md)

[Get-AzureDisk](./Get-AzureDisk.md)

[Update-AzureDisk](./Update-AzureDisk.md)


