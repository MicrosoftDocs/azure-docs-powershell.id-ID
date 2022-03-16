---
external help file: Microsoft.Azure.PowerShell.Cmdlets.EventHub.dll-Help.xml
Module Name: Az.EventHub
online version: https://docs.microsoft.com/powershell/module/az.eventhub/get-azeventhub
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/Get-AzEventHub.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EventHub/EventHub/help/Get-AzEventHub.md
ms.openlocfilehash: 27282dc2e32ee534d4ef7dfea26503f660d7d63f
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140208359"
---
# Get-AzEventHub

## SYNOPSIS
Dapatkan detail tentang satu Hub Acara, atau dapatkan daftar Hub Acara.

## SYNTAX

### EventhubPropertiesSet (Default)
```
Get-AzEventHub [-ResourceGroupName] <String> [-Namespace] <String> [[-Name] <String>] [-MaxCount <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### NamespaceInputObjectSet
```
Get-AzEventHub [[-Name] <String>] [-NamespaceObject] <PSNamespaceAttributes>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzEventHub akan mengembalikan detail Hub Kejadian, atau daftar semua Hub Acara dalam ruang nama saat ini.
Jika nama Hub Acara disediakan, detail dari sebuah Hub Acara akan dikembalikan.
Jika nama Hub Acara tidak disediakan, daftar semua Hub Acara di ruang nama yang ditentukan akan dikembalikan.

## EXAMPLES

### Contoh 1: EventHub ditentukan
```powershell
PS C:\> Get-AzEventHub -ResourceGroupName MyResourceGroupName -NamespaceName MyNamespaceName -EventHubName MyEventHubName
```

Mengembalikan detail Event Hub \`MyEventHubName\`.

### Contoh 2: Daftar EventHub dalam Namespace yang ditentukan
```powershell
PS C:\> Get-AzEventHub -ResourceGroup MyResourceGroupName -NamespaceName MyNamespaceName
```

Mengembalikan daftar Hub Acara di ruang nama MyNamespaceName\`\`.

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

### -MaxCount
Menentukan jumlah maksimum EventHubs untuk dikembalikan.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: EventhubPropertiesSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama EventHub

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: EventHubName

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace
Nama Kumpulan Nama

```yaml
Type: System.String
Parameter Sets: EventhubPropertiesSet
Aliases: NamespaceName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NamespaceObject
Objek kumpulan nama

```yaml
Type: Microsoft.Azure.Commands.EventHub.Models.PSNamespaceAttributes
Parameter Sets: NamespaceInputObjectSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

```yaml
Type: System.String
Parameter Sets: EventhubPropertiesSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.EventHub.Models.PSEventHubAttributes

## CATATAN

## RELATED LINKS
