---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/get-azeventgridtopictype
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridTopicType.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridTopicType.md
ms.openlocfilehash: 6bb09ba3ae6f0483f3881df42c873e53e077f8fc
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144733474"
---
# Get-AzEventGridTopicType

## SYNOPSIS
Mendapatkan detail tentang jenis topik yang didukung oleh Azure Event Grid.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.eventgrid/get-azeventgridtopictype) untuk informasi terbaru.

## SYNTAX

```
Get-AzEventGridTopicType [-Name <String>] [-IncludeEventTypeData] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail jenis topik yang didukung oleh Azure Event Grid.
Jika nama jenis topik ditentukan, detail tentang jenis topik tersebut dikembalikan.
Jika nama jenis topik tidak ditentukan, detail tentang semua jenis topik dikembalikan.
Jika IncludeEventTypes ditentukan, informasi tentang jenis peristiwa yang didukung oleh setiap jenis topik disertakan dalam respons.

## EXAMPLES

### Contoh 1
```powershell
Get-AzEventGridTopicType
```

Mendapatkan daftar jenis topik.

### Contoh 2
```powershell
Get-AzEventGridTopicType -Name "Microsoft.Storage.StorageAccounts"
```

Mendapatkan informasi tentang jenis topik StorageAccounts.

### Contoh 3
```powershell
Get-AzEventGridTopicType -Name "Microsoft.Storage.StorageAccounts" -IncludeEventTypeData
```

Mendapatkan informasi tentang jenis topik StorageAccounts, termasuk jenis peristiwa yang didukung oleh StorageAccounts.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -IncludeEventTypeData
Jika ditentukan, respons akan menyertakan jenis peristiwa yang didukung oleh jenis topik.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama Jenis Topik EventGrid.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSTopicTypeInfoListInstance

### Microsoft.Azure.Commands.EventGrid.Models.PSTopicTypeInfo

## NOTES

## RELATED LINKS
