---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 98CB62E1-0A18-4207-81FA-07CC60310896
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermfirewallfqdntag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmFirewallFqdnTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmFirewallFqdnTag.md
ms.openlocfilehash: 33482ff6686409c62a2aeffbf616f62074b1984e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142791803"
---
# Get-AzureRmFirewallFqdnTag

## SYNOPSIS
Dapatkan Azure Firewall Fqdn Tag yang tersedia.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmFirewallFqdnTag [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmFirewallFqdnTag** mendapatkan daftar Tag FQDN yang dapat digunakan untuk Aturan Aplikasi Azure Firewall

## EXAMPLES

### 1: Ambil semua Tag FQDN yang tersedia
```
Get-AzureRmFirewallFqdnTag
```

Contoh ini mengambil semua Tag FQDN yang tersedia.

### 2: Menggunakan Tag FQDN pertama yang tersedia dalam Aturan Aplikasi
```
$fqdnTags = Get-AzureRmFirewallFqdnTag
New-AzureRmFirewallApplicationRule -Name AR -SourceAddress * -FqdnTag $fqdnTags[0].FqdnTagName
```

Contoh ini membuat Aturan Aplikasi Firewall menggunakan Tag FQDN pertama yang tersedia

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewallFqdnTag

## NOTES

## RELATED LINKS

[New-AzureRmFirewallApplicationRule](./New-AzureRmFirewallApplicationRule.md)

[New-AzureRmFirewall](./New-AzureRmFirewall.md)
