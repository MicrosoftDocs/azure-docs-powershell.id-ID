---
external help file: Microsoft.Azure.Commands.ResourceManager.Cmdlets.dll-Help.xml
Module Name: AzureRM.Resources
ms.assetid: EFBBFB60-D972-47B8-997E-B737F0CA007E
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Find-AzureRmResourceGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Resources/Commands.Resources/help/Find-AzureRmResourceGroup.md
ms.openlocfilehash: 029404938ba7a253b5130f5c807e4b66c3847d43
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132419742"
---
# Find-AzureRmResourceGroup

## SYNOPSIS
Mencari grup sumber daya.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Find-AzureRmResourceGroup [-Tag <Hashtable>] [-ApiVersion <String>] [-Pre]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Find-AzureRmResourceGroup** mencari grup sumber daya menggunakan parameter yang ditentukan.

## EXAMPLES

### Contoh 1: Menemukan semua grup sumber daya
```
PS C:\>Find-AzureRmResourceGroup
```

Perintah ini menemukan semua grup sumber daya.

### Contoh 2: Temukan grup sumber daya menurut nama tag
```
PS C:\>Find-AzureRmResourceGroup -Tag @{ "testtag" = $null }
```

Perintah ini menemukan semua grup sumber daya yang memiliki tag bernama testtag.

### Contoh 3: Temukan grup sumber daya menurut nama tag dan nilai
```
PS C:\>Find-AzureRmResourceGroup -Tag @{"testtag" = "testval" }
```

Perintah ini menemukan semua grup sumber daya yang memiliki tag bernama testtag dan nilai testval.

## PARAMETERS

### -ApiVersion
Menentukan versi API penyedia sumber daya untuk digunakan. Jika Anda tidak menentukan versi, cmdlet ini menggunakan versi terbaru yang tersedia.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pra
Mengindikasikan bahwa cmdlet ini mempertimbangkan versi API prari perilisan bila secara otomatis menentukan versi mana yang akan digunakan.

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

### -Tag
Menentukan informasi tag, sebagai tabel hash, untuk memfilter hasil Anda. Gunakan format berikut:

@{tagName=$null} atau @{tagName = 'tagValue'}.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

### System.Management.Automation.PSObject

## CATATAN

## RELATED LINKS

