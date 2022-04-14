---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 895F9A5F-D48F-403D-BD8F-72D72D420690
online version: ''
schema: 2.0.0
ms.openlocfilehash: fec31914f8a96dccdfa76caa70e18faa45ccfc26
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142243736"
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

### Contoh 1: Memperbarui konfigurasi jaringan langganan Azure ke file lokal
```
PS C:\> Set-AzureVNetConfig  -ConfigurationPath "c:\temp\MyAzNets.netcfg"
```

Perintah ini memperbarui konfigurasi jaringan langganan Microsoft Azure saat ini ke dalam file lokal "c:\temp\MyAzNets.netcfg".

### Contoh 2: Atur langganan Azure lalu perbarui konfigurasi jaringan
```
PS C:\> $SubsId = "5bea2bc2-88a5-44b8-abe1-3e76733b6783"
C:\PS> $Cert = Get-Item cert:\LocalMachine\MY\82F105B2DA81149204A6257A9A91EC452B8C52C3
C:\PS> Set-AzureVNetConfig  -ConfigurationPath "c:\temp\MyAzNets.netcfg"
```

Contoh ini mengatur langganan Microsoft Azure, lalu memperbarui konfigurasi jaringan langganan tersebut menggunakan konfigurasi yang ditentukan dalam file lokal "c:\temp\MyAzNets.netcfg".

## PARAMETERS

### -ConfigurationPath
Menentukan jalur dan nama file dari file konfigurasi jaringan (.netcfg).

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

## CATATAN

## RELATED LINKS

[Get-AzureVNetConfig](./Get-AzureVNetConfig.md)

[Get-AzureVNetSite](./Get-AzureVNetSite.md)

[Hapus-AzureVNetConfig](./Remove-AzureVNetConfig.md)


