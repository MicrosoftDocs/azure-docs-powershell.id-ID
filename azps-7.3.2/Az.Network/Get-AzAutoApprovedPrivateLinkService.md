---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azautoapprovedprivatelinkservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzAutoApprovedPrivateLinkService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzAutoApprovedPrivateLinkService.md
ms.openlocfilehash: c0c8b350dd4e2c1f7247ce593424992c9e8445b0
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142763488"
---
# Get-AzAutoApprovedPrivateLinkService

## SYNOPSIS
Mendapatkan array id layanan tautan pribadi yang dapat ditautkan ke titik akhir privat dengan disetujui otomatis.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/get-azautoapprovedprivatelinkservice) untuk informasi terbaru.

## SYNTAX

```
Get-AzAutoApprovedPrivateLinkService -Location <String> [-ResourceGroupName <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Get-AzAutoApprovedPrivateLinkService** mendapatkan array id layanan tautan pribadi yang dapat ditautkan ke titik akhir pribadi dengan disetujui otomatis.

## EXAMPLES

### Contoh
```
Get-AzAutoApprovedPrivateLinkService -Location westus -ResourceGroupName TestResourceGroup
```

Contoh ini mengembalikan array id layanan tautan privat yang dapat ditautkan ke titik akhir privat dengan disetujui otomatis.

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

### -Lokasi
```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSAutoApprovedPrivateLinkService

## NOTES

## RELATED LINKS
