---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: 6424B740-DBFB-490C-AEAA-EDD60952B435
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Get-AzureRmProviderOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Get-AzureRmProviderOperation.md
ms.openlocfilehash: d4e58e1fc2da68d9293afa27072a4cf32023f661
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423842"
---
# Get-AzureRmProviderOperation

## SYNOPSIS
Dapatkan operasi untuk penyedia sumber daya Azure yang dapat mengamankan menggunakan Azure RBAC.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmProviderOperation [-OperationSearchString] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Sumber Get-AzureRmProviderOperation operasi yang diekspos oleh penyedia sumber daya Azure.
Operasi bisa dibuat untuk membuat peran kustom di Azure RBAC.
Perintah akan mengambil sebagai input string pencarian operasi (dengan karakter wildcard(*) yang menentukan detail operasi untuk ditampilkan.

Gunakan Get-AzureRmProviderOperation * untuk mendapatkan semua operasi bagi semua penyedia sumber daya Azure.

Gunakan Get-AzureRmProviderOperation Microsoft.Compute/* untuk mendapatkan semua operasi penyedia sumber daya Microsoft.Compute.

## EXAMPLES

### -------------------------- Dapatkan semua tindakan untuk semua --------------------------
```
PS C:\> Get-AzureRmProviderOperation *
```

### -------------------------- Dapatkan tindakan untuk penyedia sumber daya tertentu --------------------------
```
PS C:\> Get-AzureRmProviderOperation Microsoft.Insights/*
```

### -------------------------- Mendapatkan semua tindakan yang dapat dilakukan pada komputer virtual --------------------------
```
PS C:\> Get-AzureRmProviderOperation */virtualMachines/*
```

## PARAMETERS

### -OperationSearchString
String pencarian operasi (dengan kemungkinan karakter wildcard (*))

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### String
Parameter 'OperationSearchString' menerima nilai tipe 'String' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.PSResourceProviderOperation

## CATATAN
Kata kunci: azure, azurerm, arm, resource, management, manager, resource, group, template, deployment

## RELATED LINKS

