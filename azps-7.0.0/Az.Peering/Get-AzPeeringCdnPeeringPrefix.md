---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Peering.dll-Help.xml
Module Name: Az.Peering
online version: https://docs.microsoft.com/powershell/module/az.peering/get-azpeeringcdnpeeringprefix
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Peering/Peering/help/Get-AzPeeringCdnPeeringPrefix.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Peering/Peering/help/Get-AzPeeringCdnPeeringPrefix.md
ms.openlocfilehash: 3d43858c0b938ebad1490bc121c15ca8cd1653ac
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136547444"
---
# Get-AzPeeringCdnPeeringPrefix

## SYNOPSIS
Mencantumkan semua prefiks yang diiklankan untuk cdn di lokasi peering tertentu

## SYNTAX

```
Get-AzPeeringCdnPeeringPrefix [-PeeringLocation] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan semua prefiks yang diiklankan untuk cdn di lokasi peering tertentu

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzPeeringCdnPeeringPrefix -PeeringLocation "Seattle"
```

Mencantumkan semua prefiks yang diiklankan untuk cdn di lokasi peering fisik yang ditentukan

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PeeringLocation
Lokasi Fisik Berbeda dari Azure Region.
Gunakan Get-AzPeeringLocation -Jenis gunakan Nama Kota sebagai kunci untuk memeriksa apakah lokasi peering sudah ada atau Gunakan Get-AzPeeringLocation -Kind untuk mendapatkan semua lokasi \<kind\> \<kind\> peering untuk dipilih.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Peering.Models.PSCdnPeeringPrefix

## CATATAN

## RELATED LINKS
