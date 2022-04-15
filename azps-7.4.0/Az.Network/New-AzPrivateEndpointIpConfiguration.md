---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPrivateEndpointIpConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzPrivateEndpointIpConfiguration.md
ms.openlocfilehash: 91a16eed6b065694bdd3a13fedcddcbad28296e3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142176487"
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
New-AzPrivateEndpointIpConfiguration -Name "IpConfigurationForPrivateEndpoint" -PrivateIPAddress "10.0.0.10"
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
ID grup tempat titik akhir privat tersambung.

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
Nama anggota grup tempat titik akhir privat tersambung.

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
Alamat ip pribadi subnet titik akhir privat.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSPrivateEndpointIPConfiguration

## CATATAN

## RELATED LINKS
