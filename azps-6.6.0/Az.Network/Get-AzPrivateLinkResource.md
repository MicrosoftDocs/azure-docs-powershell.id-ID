---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azprivatelinkresource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzPrivateLinkResource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzPrivateLinkResource.md
ms.openlocfilehash: 2f30318214fafefb88bcd335cc9b2782b5871158
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142268971"
---
# Get-AzPrivateLinkResource

## SYNOPSIS
Mendapatkan sumber daya tautan pribadi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/get-azprivatelinkresource) untuk informasi terbaru.

## SYNTAX

### ByPrivateLinkResourceId (Default)
```
Get-AzPrivateLinkResource -PrivateLinkResourceId <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByResource
```
Get-AzPrivateLinkResource -ResourceGroupName <String> -ServiceName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [-PrivateLinkResourceType <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzPrivateLinkResource** mengambil semua sumber daya tautan milik PrivateLinkResource.

## EXAMPLES

### Contoh 1
```
Get-AzPrivateLinkResource -PrivateLinkResourceId '/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/TestResourceGroup/providers/Microsoft.Sql/servers/mySql'
```

Contoh ini mencantumkan semua sumber daya link pribadi nbelong ke sql server bernama mySql.

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

### -Nama
Nama sumber daya tautan privat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: GroupName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrivateLinkResourceId
Id manajer sumber daya Azure dari sumber daya tautan privat.

```yaml
Type: System.String
Parameter Sets: ByPrivateLinkResourceId
Aliases: PrivateLinkServiceId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrivateLinkResourceType
Tipe sumber daya tautan privat.

```yaml
Type: System.String
Parameter Sets: ByResource
Aliases:
Accepted values:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Nama layanan tautan privat.

```yaml
Type: System.String
Parameter Sets: ByResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
