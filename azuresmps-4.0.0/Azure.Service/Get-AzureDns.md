---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 184FB33A-C866-4AF0-BA31-8ADCFC6EE8E2
online version: ''
schema: 2.0.0
ms.openlocfilehash: 367585753575ed07c2a12345ab80fd30c3f558b2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142279177"
---
# Get-AzureDns

## SYNOPSIS
Mendapatkan pengaturan DNS untuk penyebaran Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureDns [-DnsSettings <DnsSettings>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureDns** mendapatkan pengaturan DNS untuk penyebaran Azure.
Cmdlet mengembalikan nama yang mudah dikenali dan alamat IP server DNS dalam objek pengaturan DNS.

## EXAMPLES

### Contoh 1: Mendapatkan pengaturan DNS
```
PS C:\> Get-AzureDeployment -ServiceName "ContosoService" -Slot "Production" | Get-AzureDNS
```

Perintah ini menggunakan cmdlet **Get-AzureDeployment** untuk mendapatkan penyebaran produksi layanan bernama ContosoService.
Perintah melewati objek tersebut ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini akan mendapatkan pengaturan DNS.

## PARAMETERS

### -DnsSettings
Menentukan objek **DnsSettings** .

```yaml
Type: DnsSettings
Parameter Sets: (All)
Aliases: InputObject

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureDns](./Add-AzureDns.md)

[Get-AzureDeployment](./Get-AzureDeployment.md)

[AzureDns baru](./New-AzureDns.md)

[Hapus AzureDns](./Remove-AzureDns.md)

[Set-AzureDns](./Set-AzureDns.md)


