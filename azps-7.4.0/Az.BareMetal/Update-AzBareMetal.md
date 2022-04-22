---
external help file: ''
Module Name: Az.BareMetal
online version: https://docs.microsoft.com/powershell/module/az.baremetal/update-azbaremetal
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/BareMetal/help/Update-AzBareMetal.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/BareMetal/help/Update-AzBareMetal.md
ms.openlocfilehash: 8b14b64afbb75b7af295d6207cd135964f49b2aa
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142878796"
---
# Update-AzBareMetal

## SYNOPSIS
Menambal bidang Tag instans Azure BareMetal untuk langganan, grup sumber daya, dan nama instans tertentu.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzBareMetal -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzBareMetal -InputObject <IBareMetalIdentity> [-Tag <Hashtable>] [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menambal bidang Tag instans Azure BareMetal untuk langganan, grup sumber daya, dan nama instans tertentu.

## EXAMPLES

### Contoh 1: UpdateExpanded
```powershell
Update-AzBareMetal -Name oraclerac53 -ResourceGroupName SAT09A-T530 -Tag @{"env"="test"}
```

```output
Location       Name        ResourceGroupName
--------       ----        -----------------
southcentralus oraclerac53 SAT09A-T530
```

Menambal bidang Tag instans Azure BareMetal untuk langganan, grup sumber daya, dan nama instans tertentu.

### Contoh 2: UpdateViaIdentityExpanded
```powershell
Get-AzBareMetal -Name oraclerac53 -ResourceGroupName SAT09A-T530 | Update-AzBareMetal -Tag @{"env"="test"}
```

```output
Location       Name        ResourceGroupName
--------       ----        -----------------
southcentralus oraclerac53 SAT09A-T530
```

Menambal bidang Tag instans Azure BareMetal untuk langganan, grup sumber daya, dan nama instans tertentu.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.BareMetal.Models.IBareMetalIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama Azure BareMetal di instans Azure.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: AzureBareMetalInstanceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

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
ID langganan target.

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
Bidang tag instans AzureBareMetal.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.BareMetal.Models.IBareMetalIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.BareMetal.Models.Api20210809.IAzureBareMetalInstance

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IBareMetalIdentity>: Parameter Identitas
  - `[AzureBareMetalInstanceName <String>]`: Nama Azure BareMetal pada instans Azure.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

