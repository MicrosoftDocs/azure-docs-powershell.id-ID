---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventGrid.dll-Help.xml
Module Name: Az.EventGrid
online version: https://docs.microsoft.com/en-us/powershell/module/az.eventgrid/get-azeventgridtopictype
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/EventGrid/EventGrid/help/Get-AzEventGridTopicType.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/EventGrid/EventGrid/help/Get-AzEventGridTopicType.md
ms.openlocfilehash: e2cd8cfeadf0c9574cbf39a642133109aa02ec39
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136012810"
---
# Get-AzEventGridTopicType

## SYNOPSIS
Mendapatkan detail tentang tipe topik yang didukung oleh Kisi Acara Azure.

## SINTAKS

```
Get-AzEventGridTopicType [-Name <String>] [-IncludeEventTypeData] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESKRIPSI
Mendapatkan detail tipe topik yang didukung oleh Kisi Acara Azure.
Jika nama tipe topik ditentukan, detail tentang tipe topik tersebut akan dikembalikan.
Jika nama tipe topik tidak ditentukan, detail tentang semua tipe topik akan dikembalikan.
Jika IncludeEventTypes ditentukan, informasi tentang tipe kejadian yang didukung oleh setiap tipe topik disertakan dalam respons.

## CONTOH

### Contoh 1
```powershell
PS C:\> Get-AzEventGridTopicType
```

Mendapatkan daftar tipe topik.

### Contoh 2
```powershell
PS C:\> Get-AzEventGridTopicType -Name "Microsoft.Storage.StorageAccounts"
```

Mendapatkan informasi tentang tipe topik StorageAccounts.

### Contoh 3
```powershell
PS C:\> Get-AzEventGridTopicType -Name "Microsoft.Storage.StorageAccounts" -IncludeEventTypeData
```

Mendapatkan informasi tentang tipe topik StorageAccounts, termasuk tipe acara yang didukung oleh StorageAccounts.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.EventGrid.Models.PSTopicTypeInfoListInstance

### Microsoft.Azure.Commands.EventGrid.Models.PSTopicTypeInfo

## CATATAN

## LINK TERKAIT
