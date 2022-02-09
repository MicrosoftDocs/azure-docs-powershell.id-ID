---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPrivateEndpointIpConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPrivateEndpointIpConfiguration.md
ms.openlocfilehash: 6c2a8fe3b07ee7e4bd9dfb9f98765ec9285ad58f
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138292059"
---
# New-AzPrivateEndpointIpConfiguration

## SYNOPSIS
Membuat objek IpConfiguration untuk titik akhir privat.

## SYNTAX

```
New-AzPrivateEndpointIpConfiguration -Name <String> [-GroupId <String>] [-MemberName <String>]
 -PrivateIpAddress <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzPrivateEndpointIpConfiguration** membuat objek IpConfiguration untuk titik akhir privat.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzPrivateEndpointIpConfiguration -Name "IpConfigurationForPrivateEndpoint" -PrivateIPAddress "10.0.0.10"
```

Contoh ini membuat objek IpConfiguration yang digunakan untuk titik akhir privat.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupId
ID grup yang tersambung dengan titik akhir privat.

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

### -MemberName
Nama anggota grup yang tersambung dengan titik akhir privat.

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

### -Nama
Nama konfigurasi IP titik akhir privat.

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

### -PrivateIpAddress
Alamat ip privat subnet titik akhir privat.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSPrivateEndpointIPConfiguration

## CATATAN

## RELATED LINKS
