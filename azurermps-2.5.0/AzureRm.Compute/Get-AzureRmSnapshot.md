---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/get-azurermsnapshot
schema: 2.0.0
ms.openlocfilehash: 1595d6bf5cec76fd0e243cf5a44669ee9d23c01c596fe7ffea92b7c4d58974a6
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140857646"
---
# Get-AzureRmSnapshot

## SYNOPSIS
Mendapatkan properti snapshot

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmSnapshot [[-ResourceGroupName] <String>] [[-SnapshotName] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmSnapshot** mendapatkan properti snapshot.

## EXAMPLES

### Contoh 1
```
PS C:\> Get-AzureRmSnapshot
```

Perintah ini mendapatkan properti dari semua snapshot langganan.

### Contoh 2
```
PS C:\> Get-AzureRmSnapshot -ResourceGroupName "ResourceGroupName1"
```

Perintah ini mendapatkan properti semua snapshot dalam grup sumber daya yang bernama "ResourceGroupName1"

### Contoh 3
```
PS C:\> Get-AzureRmSnapshot -ResourceGroupName "ResourceGroupName1" -SnapshotName "SnapshotName1"
```

Perintah ini mendapatkan properti snapshot yang bernama "SnapshotName1" dalam grup sumber daya bernama "ResourceGroupName1"

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SnapshotName
Menentukan nama snapshot.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSSnapshot

## CATATAN

## RELATED LINKS

