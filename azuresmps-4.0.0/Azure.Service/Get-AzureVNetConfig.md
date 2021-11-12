---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: F34910FA-B024-4C1C-B040-671C8962C49D
online version: ''
schema: 2.0.0
ms.openlocfilehash: 86a0fd31f5705586065d69a7bde7be6359a705e2
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428078"
---
# Get-AzureVNetConfig

## SYNOPSIS
Mendapatkan konfigurasi jaringan virtual Azure dari langganan saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureVNetConfig [-ExportToFile <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureVNetConfig** mengambil konfigurasi jaringan virtual dari langganan Azure saat ini.
Jika parameter *ExportToFile* ditentukan, file konfigurasi jaringan akan dibuat.

## EXAMPLES

### Contoh 1: Mendapatkan konfigurasi jaringan virtual dari langganan Azure saat ini
```
PS C:\> Get-AzureVNetConfig
```

Perintah ini mendapatkan konfigurasi jaringan virtual dari langganan Azure saat ini dan menampilkannya.

### Contoh 2: Mendapatkan konfigurasi jaringan virtual dari langganan Azure saat ini dan menyimpannya ke file lokal
```
PS C:\> Get-AzureVNetConfig -ExportToFile "c:\temp\MyAzNets.netcfg"
```

Perintah ini mendapatkan konfigurasi jaringan virtual dari langganan Azure saat ini, kemudian menyimpannya ke file lokal.

## PARAMETERS

### -ExportToFile
Menentukan jalur dan nama file file konfigurasi jaringan yang akan dibuat dari pengaturan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

[Get-AzureVNetSite](./Get-AzureVNetSite.md)

[Remove-AzureVNetConfig](./Remove-AzureVNetConfig.md)

[Set-AzureVNetConfig](./Set-AzureVNetConfig.md)


