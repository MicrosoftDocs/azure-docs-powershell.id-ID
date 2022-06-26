---
external help file: ''
Module Name: Az.CustomProviders
online version: https://docs.microsoft.com/powershell/module/az.customproviders/update-azcustomprovider
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomProviders/help/Update-AzCustomProvider.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CustomProviders/help/Update-AzCustomProvider.md
ms.openlocfilehash: 11e429d6118f1972a2bb7c0614e4b3da453b2a4f
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146620480"
---
# Update-AzCustomProvider

## SYNOPSIS
Updates penyedia sumber daya kustom yang sudah ada.
Satu-satunya nilai yang dapat diperbarui melalui PATCH saat ini adalah tag.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.customproviders/update-azcustomprovider) untuk informasi terbaru.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzCustomProvider -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzCustomProvider -InputObject <ICustomProvidersIdentity> [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Updates penyedia sumber daya kustom yang sudah ada.
Satu-satunya nilai yang dapat diperbarui melalui PATCH saat ini adalah tag.

## EXAMPLES

### Contoh 1: Menambahkan Tag ke Penyedia kustom
```powershell
Update-AzCustomProvider -ResourceGroupName myRg -Name Namespace.Type -Tag @{MyTag="MyValue"} | Format-List
```

```output
Action            :
Id                : /subscriptions/xxxxx-yyyyy-xxxx-yyyy/resourceGroups/mc-cp01/providers/Microsoft.CustomProviders/resourceproviders/Namespace.Type
Location          : West US 2
Name              : Namespace.Type
ProvisioningState : Succeeded
ResourceType      : {CustomRoute1, associations}
Tag               : Microsoft.Azure.PowerShell.Cmdlets.CustomProviders.Models.Api20180901Preview.ResourceTags
Type              : Microsoft.CustomProviders/resourceproviders
Validation        :
```

Perbarui tag penyedia kustom.

### Contoh 2: Memperbarui penyedia kustom dengan pipa
```powershell
Get-AzCustomProvider -ResourceGroupName myRg -Name Namespace.Type | Update-AzCustomProvider -Tag @{MyTag="MyValue"}
```

```output
Location  Name             Type
--------  ----             ----
West US 2 Namespace.Type   Microsoft.CustomProviders/resourceproviders
```

Perbarui penyedia kustom menggunakan pipa.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CustomProviders.Models.ICustomProvidersIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama penyedia sumber daya.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: ResourceProviderName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Atur ID Langganan Azure.
Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-00000000000)

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CustomProviders.Models.ICustomProvidersIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CustomProviders.Models.Api20180901Preview.ICustomRpManifest

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<ICustomProvidersIdentity>`: Parameter Identitas
  - `[AssociationName <String>]`: Nama asosiasi.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya.
  - `[ResourceProviderName <String>]`: Nama penyedia sumber daya.
  - `[Scope <String>]`: Ruang lingkup asosiasi.
  - `[SubscriptionId <String>]`: ID langganan Azure. Ini adalah string berformat GUID (misalnya 000000000-0000-0000-0000-00000000000)

## RELATED LINKS

