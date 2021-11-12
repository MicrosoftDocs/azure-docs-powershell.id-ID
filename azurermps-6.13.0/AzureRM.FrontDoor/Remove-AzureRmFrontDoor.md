---
external help file: Microsoft.Azure.Commands.FrontDoor.dll-Help.xml
Module Name: AzureRM.FrontDoor
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.frontdoor/remove-azurermfrontdoor
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/FrontDoor/Commands.FrontDoor/help/Remove-AzureRmFrontDoor.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/FrontDoor/Commands.FrontDoor/help/Remove-AzureRmFrontDoor.md
ms.openlocfilehash: 8eae5034080bd1035cfe7e8331ca015820688e63
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132419964"
---
# Remove-AzureRmFrontDoor

## SYNOPSIS
Hapus Penyeimbang muat Pintu Depan

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByFieldsParameterSet (Default)
```
Remove-AzureRmFrontDoor -ResourceGroupName <String> -Name <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectParameterSet
```
Remove-AzureRmFrontDoor -InputObject <PSFrontDoor> [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdParameterSet
```
Remove-AzureRmFrontDoor -ResourceId <String> [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmFrontDoor** menghapus penyeimbang muat Front Door di bawah langganan saat ini

## EXAMPLES

### Contoh 1: Hapus "frontdoor1" di grup sumber daya "rg1" di bawah langganan saat ini.
```powershell
PS C:\> Remove-AzureRmFrontDoor -Name "frontdoor1" -ResourceGroupName "rg1"
```

Hapus "frontdoor1" di grup sumber daya "rg1" di bawah langganan saat ini.

### Contoh 2: Hapus semua FrontDoors in resource group "rg1" di bawah langganan saat ini.
```powershell
PS C:\> Get-AzureRmFrontDoor -ResourceGroupName "rg1" | Remove-AzureRmFrontDoor
```

Hapus semua FrontDoors di grup sumber daya "rg1" di bawah langganan saat ini.

### Contoh 3: Hapus semua FrontDoors di bawah langganan saat ini.
```powershell
PS C:\> Get-AzureRmFrontDoor | Remove-AzureRmFrontDoor
```

Hapus semua FrontDoors di bawah langganan saat ini.

### Contoh 4: Hapus semua FrontDoors dengan nama "frontdoor1" di bawah langganan saat ini.
```powershell
PS C:\> Remove-AzureRmFrontDoor -Name "frontdoor1" | Remove-AzureRmFrontDoor
```

Hapus semua FrontDoors dengan nama "frontdoor1" di bawah langganan saat ini.

## PARAMETERS

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

### -InputObject
Objek Pintu Depan yang akan dihapus.

```yaml
Type: Microsoft.Azure.Commands.FrontDoor.Models.PSFrontDoor
Parameter Sets: ByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Pintu Depan untuk dihapus.

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Objek yang dikembalikan (jika ditentukan).

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

### -ResourceGroupName
Grup sumber daya tempat Pintu Depan berada.

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya dari Pintu Depan untuk dihapus

```yaml
Type: System.String
Parameter Sets: ResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.FrontDoor.Models.PSFrontDoor

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS

[New-AzureRmFrontDoor](./New-AzureRmFrontDoor.md) 
 [Get-AzureRmFrontDoor](./Get-AzureRmFrontDoor.md)
