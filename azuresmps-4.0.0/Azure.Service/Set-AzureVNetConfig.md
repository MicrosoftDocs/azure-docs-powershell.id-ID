---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 895F9A5F-D48F-403D-BD8F-72D72D420690
online version: ''
schema: 2.0.0
ms.openlocfilehash: c69f58923baa4528d3f3edf48de3b01d86368ee48f5e63547c56edbcbad22c31
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417697"
---
# Set-AzureVNetConfig

## SYNOPSIS
Memperbarui pengaturan jaringan virtual untuk layanan cloud Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureVNetConfig [-ConfigurationPath] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureVNetConfig** memperbarui konfigurasi jaringan untuk langganan Azure saat ini dengan menentukan jalur ke file konfigurasi jaringan (.netcfg).
File konfigurasi jaringan menentukan server DNS dan subnet untuk layanan awan dalam langganan.

## EXAMPLES

### Contoh 1: Perbarui konfigurasi jaringan langganan Azure ke file lokal
```
PS C:\> Set-AzureVNetConfig  -ConfigurationPath "c:\temp\MyAzNets.netcfg"
```

Perintah ini akan memperbarui konfigurasi jaringan langganan Microsoft Azure pada file lokal "c:\temp\MyAzNets.netcfg".

### Contoh 2: Atur langganan Azure, lalu perbarui konfigurasi jaringan
```
PS C:\> $SubsId = "5bea2bc2-88a5-44b8-abe1-3e76733b6783"
C:\PS> $Cert = Get-Item cert:\LocalMachine\MY\82F105B2DA81149204A6257A9A91EC452B8C52C3
C:\PS> Set-AzureVNetConfig  -ConfigurationPath "c:\temp\MyAzNets.netcfg"
```

Contoh ini mengatur Microsoft Azure lokal, lalu memperbarui konfigurasi jaringan langganan tersebut menggunakan konfigurasi yang ditentukan dalam file lokal "c:\temp\MyAzNets.netcfg".

## PARAMETERS

### -ConfigurationPath
Menentukan jalur dan nama file file file konfigurasi jaringan (.netcfg).

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[Get-AzureVNetConfig](./Get-AzureVNetConfig.md)

[Get-AzureVNetSite](./Get-AzureVNetSite.md)

[Remove-AzureVNetConfig](./Remove-AzureVNetConfig.md)


