---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 4E19A767-8233-42A0-95C5-1547B4DF297E
online version: ''
schema: 2.0.0
ms.openlocfilehash: d1c2a660d44a1aef184b3314c897d24ccf32baef
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142095093"
---
# Get-AzureNetworkSecurityGroup

## SYNOPSIS
Mendapatkan detail untuk grup keamanan jaringan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureNetworkSecurityGroup [-Name <String>] [-Detailed] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureNetworkSecurityGroup** mengembalikan detail untuk grup keamanan jaringan Azure.
Tentukan parameter *Mendetail* untuk menampilkan aturan keamanan jaringan.

## EXAMPLES

## PARAMETERS

### -Detail
Menunjukkan bahwa cmdlet ini mengembalikan aturan keamanan jaringan untuk grup keamanan jaringan.

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

### -Nama
Menentukan nama grup keamanan jaringan yang didapat cmdlet ini.

> [!NOTE]
> Ketika grup keamanan jaringan klasik dibuat dalam grup sumber daya selain ***Jaringan Default*** menggunakan portal Azure, Anda harus menggunakan sintaks PowerShell berikut: `Get-AzureNetworkSecurityGroup -Name 'Group myResouceGroup myNetworkSecurityGroup'`.

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

[AzureNetworkSecurityGroup baru](./New-AzureNetworkSecurityGroup.md)

[Remove-AzureNetworkSecurityGroup](./Remove-AzureNetworkSecurityGroup.md)

