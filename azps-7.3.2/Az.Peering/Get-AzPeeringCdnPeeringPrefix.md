---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Peering.dll-Help.xml
Module Name: Az.Peering
online version: https://docs.microsoft.com/powershell/module/az.peering/get-azpeeringcdnpeeringprefix
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Peering/Peering/help/Get-AzPeeringCdnPeeringPrefix.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Peering/Peering/help/Get-AzPeeringCdnPeeringPrefix.md
ms.openlocfilehash: adb2ca697075ecd5584cdb6ed3024bbdbcdde0dd
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143073287"
---
# Get-AzPeeringCdnPeeringPrefix

## SYNOPSIS
Mencantumkan semua prefiks yang diiklankan untuk cdn di lokasi peering yang ditentukan

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.peering/get-azpeeringcdnpeeringprefix) untuk informasi terbaru.

## SYNTAX

```
Get-AzPeeringCdnPeeringPrefix [-PeeringLocation] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan semua prefiks yang diiklankan untuk cdn di lokasi peering yang ditentukan

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzPeeringCdnPeeringPrefix -PeeringLocation "Seattle"
```

Mencantumkan semua prefiks yang diiklankan untuk cdn di lokasi peering fisik tertentu

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
Lokasi Fisik Berbeda dari Kawasan Azure.
Gunakan Get-AzPeeringLocation -Kind \<kind\> gunakan Nama kota sebagai kunci untuk memeriksa apakah lokasi peering ada atau Gunakan Get-AzPeeringLocation -Kind \<kind\> untuk mendapatkan semua lokasi peering untuk memilih.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Peering.Models.PSCdnPeeringPrefix

## NOTES

## RELATED LINKS
