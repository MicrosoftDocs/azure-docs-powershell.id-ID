---
external help file: Microsoft.Azure.Commands.Resources.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: 52C5CD8B-2489-4FE6-9F33-B3350531CD8E
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.resources/get-azurermadgroupmember
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Get-AzureRmADGroupMember.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Get-AzureRmADGroupMember.md
ms.openlocfilehash: c3a783178bf8342e891f8eab2996e77a2045721a
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425512"
---
# Get-AzureRmADGroupMember

## SYNOPSIS
Mendapatkan anggota grup.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmADGroupMember [-GroupObjectId <Guid>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan anggota grup.

## EXAMPLES

### Memfilter anggota grup menggunakan id objek grup
```
PS C:\> Get-AzureRmADGroupMember -GroupObjectId 85F89C90-780E-4AA6-9F4F-6F268D322EEE
```

Mendapatkan anggota grup dengan 85F89C90-780E-4AA6-9F4F-6F268D322EEE id

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -GroupObjectId
Id objek grup.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### System.Collections.generic.List'1[Microsoft.Azure.Graph. RBAC. Version1_6.ActiveDirectory.DIRECTDObject]

## CATATAN

## RELATED LINKS

[Get-AzureRmADUser](./Get-AzureRmADUser.md)

[Get-AzureRmADServicePrincipal](./Get-AzureRmADServicePrincipal.md)

