---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 4024D20D-46DF-4ED8-A091-E6E17F840E40
online version: ''
schema: 2.0.0
ms.openlocfilehash: 960f098c34ef5e8256a5e87b753733ca7ac58a09
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143043387"
---
# Get-AzureVNetGateway

## SYNOPSIS
Mendapatkan status gateway jaringan virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureVNetGateway -VNetName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureVNetGateway** mendapatkan status gateway jaringan virtual yang sudah ada.

## EXAMPLES

### Contoh 1: Mendapatkan status gateway jaringan virtual
```
PS C:\> Get-AzureVNetGateway -VNetName "ContosoVN07"
```

Perintah ini mendapatkan status gateway jaringan virtual untuk jaringan virtual bernama ContosoVN07.

## PARAMETERS

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Menentukan jaringan virtual yang berisi gateway jaringan virtual tempat cmdlet ini mendapatkan status.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[AzureVNetGateway baru](./New-AzureVNetGateway.md)

[Hapus-AzureVNetGateway](./Remove-AzureVNetGateway.md)

[Mengatur ulang AzureVNetGateway](./Reset-AzureVNetGateway.md)

[Mengubah ukuran AzureVNetGateway](./Resize-AzureVNetGateway.md)

[Set-AzureVNetGatewayKey](./Set-AzureVNetGatewayKey.md)


