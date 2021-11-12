---
external help file: Microsoft.Azure.Commands.FrontDoor.dll-Help.xml
Module Name: AzureRM.FrontDoor
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.frontdoor/new-azurermfrontdoorfirewallpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/FrontDoor/Commands.FrontDoor/help/New-AzureRmFrontDoorFireWallPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/FrontDoor/Commands.FrontDoor/help/New-AzureRmFrontDoorFireWallPolicy.md
ms.openlocfilehash: b18f17830dd08f95c3d887ce272ff31e080001a0
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422538"
---
# New-AzureRmFrontDoorFireWallPolicy

## SYNOPSIS
Membuat kebijakan WAF

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmFrontDoorFireWallPolicy -ResourceGroupName <String> -Name <String> [-EnabledState <PSEnabledState>]
 [-Mode <PSMode>] [-Customrule <PSCustomRule[]>] [-ManagedRule <PSManagedRule[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmFrontDoorFireWallPolicy** membuat kebijakan baru Azure WAF di grup sumber daya yang ditentukan di bawah langganan saat ini

## EXAMPLES

### Contoh 1: Buat kebijakan WAF
```powershell
PS C:\>  New-AzureRmFrontDoorFireWallPolicy -Name $Name -ResourceGroupName $resourceGroupName -Customrule $customRule1 -ManagedRule $managedRule1 -En
abledState Enabled -Mode Prevention


PolicyMode         : Prevention
PolicyEnabledState : Enabled
CustomRules        : {Rule1}
ManagedRules       : {Microsoft.Azure.Commands.FrontDoor.Models.PSAzureManagedRule}
Etag               :
ProvisioningState  : Succeeded
Tags               :
Id                 : /subscriptions/{subid}/resourcegroups/{resourceGroupName}/providers/Micr
                     osoft.Network/frontdoorwebapplicationfirewallpolicies/{Name}
Name               : {Name}
Type               :
```

Membuat kebijakan WAF

## PARAMETERS

### -Customrule
Aturan kustom di dalam kebijakan

```yaml
Type: Microsoft.Azure.Commands.FrontDoor.Models.PSCustomRule[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -EnabledState
Apakah kebijakan berada dalam status diaktifkan atau status dinonaktifkan.
Kemungkinan nilai meliputi: 'Dinonaktifkan', 'Diaktifkan'

```yaml
Type: Microsoft.Azure.Commands.FrontDoor.Models.PSEnabledState
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedRule
Aturan terkelola di dalam kebijakan

```yaml
Type: Microsoft.Azure.Commands.FrontDoor.Models.PSManagedRule[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode
Menjelaskan apakah mode itu ada dalam mode deteksi atau mode pencegahan di tingkat kebijakan.
Nilai yang memungkinkan antara lain:'Pencegahan', 'Deteksi'

```yaml
Type: Microsoft.Azure.Commands.FrontDoor.Models.PSMode
Parameter Sets: (All)
Aliases:
Accepted values: Prevention, Detection

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama WebApplicationFireWallPolicy.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.FrontDoor.Models.PSPolicy

## CATATAN

## RELATED LINKS

[Set-AzureRmFrontDoorFireWallPolicy](./Set-AzureRmFrontDoorFireWallPolicy.md) 
 [Get-AzureRmFrontDoorFireWallPolicy](./Get-AzureRmFrontDoorFireWallPolicy.md) 
 [Remove-AzureRmFrontDoorFireWallPolicy](./Remove-AzureRmFrontDoorFireWallPolicy.md) 
 [New-AzureRmFrontDoorManagedRuleObject](./New-AzureRmFrontDoorManagedRuleObject.md) 
 [New-AzureRmFrontDoorCustomRuleObject](./New-AzureRmFrontDoorManagedRuleObject.md)
