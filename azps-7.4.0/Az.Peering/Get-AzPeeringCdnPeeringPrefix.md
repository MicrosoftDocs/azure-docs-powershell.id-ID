---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Peering.dll-Help.xml
Module Name: Az.Peering
online version: https://docs.microsoft.com/powershell/module/az.peering/get-azpeeringcdnpeeringprefix
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Peering/Peering/help/Get-AzPeeringCdnPeeringPrefix.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Peering/Peering/help/Get-AzPeeringCdnPeeringPrefix.md
ms.openlocfilehash: 242625250235a8f296efb8bedfdd517620d74c87
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144638162"
---
# Get-AzPeeringCdnPeeringPrefix

## SYNOPSIS
Mencantumkan semua awalan yang diiklankan untuk cdn di lokasi peering yang ditentukan

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.peering/get-azpeeringcdnpeeringprefix) untuk informasi terbaru.

## SYNTAX

```
Get-AzPeeringCdnPeeringPrefix [-PeeringLocation] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan semua awalan yang diiklankan untuk cdn di lokasi peering yang ditentukan

## EXAMPLES

### Contoh 1
```powershell
Get-AzPeeringCdnPeeringPrefix -PeeringLocation "Seattle"
```

Mencantumkan semua awalan yang diiklankan untuk cdn di lokasi peering fisik yang ditentukan

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
Lokasi Fisik Berbeda dari Wilayah Azure.
Gunakan Get-AzPeeringLocation -Kind \<kind\> gunakan Nama kota sebagai kunci untuk memeriksa apakah lokasi peering ada atau Gunakan Get-AzPeeringLocation -Kind \<kind\> untuk mendapatkan semua lokasi peering untuk dipilih.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Peering.Models.PSCdnPeeringPrefix

## NOTES

## RELATED LINKS
