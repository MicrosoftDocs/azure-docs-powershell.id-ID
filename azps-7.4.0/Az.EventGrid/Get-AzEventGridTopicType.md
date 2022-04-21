---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/powershell/module/az.eventgrid/get-azeventgridtopictype
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridTopicType.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventGrid/EventGrid/help/Get-AzEventGridTopicType.md
ms.openlocfilehash: afc5865cae562d1088bbec467bad82ae69926abf
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142748206"
---
# Get-AzEventGridTopicType

## SYNOPSIS
Mendapatkan detail tentang tipe topik yang didukung oleh Azure Event Grid.

## SYNTAX

```
Get-AzEventGridTopicType [-Name <String>] [-IncludeEventTypeData] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail tipe topik yang didukung oleh Azure Event Grid.
Jika nama tipe topik ditentukan, detail tentang tipe topik tersebut dikembalikan.
Jika nama tipe topik tidak ditentukan, detail tentang semua tipe topik dikembalikan.
Jika IncludeEventTypes ditentukan, informasi tentang tipe kejadian yang didukung oleh setiap tipe topik disertakan dalam respons.

## EXAMPLES

### Contoh 1
```powershell
Get-AzEventGridTopicType
```

Mendapatkan daftar tipe topik.

### Contoh 2
```powershell
Get-AzEventGridTopicType -Name "Microsoft.Storage.StorageAccounts"
```

Mendapatkan informasi tentang tipe topik StorageAccounts.

### Contoh 3
```powershell
Get-AzEventGridTopicType -Name "Microsoft.Storage.StorageAccounts" -IncludeEventTypeData
```

Mendapatkan informasi tentang tipe topik StorageAccounts, termasuk tipe acara yang didukung oleh StorageAccounts.

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
Jika ditentukan, respons akan menyertakan tipe acara yang didukung oleh tipe topik.

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

### -Nama
Nama Tipe Topik EventGrid.

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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.EventGrid.Models.PSTopicTypeInfoListInstance

### Microsoft.Azure.Commands.EventGrid.Models.PSTopicTypeInfo

## NOTES

## RELATED LINKS
