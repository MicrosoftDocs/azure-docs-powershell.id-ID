---
external help file: ''
Module Name: Az.Confluent
online version: https://docs.microsoft.com/powershell/module/az.confluent/update-azconfluentorganization
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Confluent/help/Update-AzConfluentOrganization.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Confluent/help/Update-AzConfluentOrganization.md
ms.openlocfilehash: c61956a3d7a8c8e2123115455e85c96126e04ff0
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138262876"
---
# Update-AzConfluentOrganization

## SYNOPSIS
Perbarui Sumber daya Organisasi

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzConfluentOrganization -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzConfluentOrganization -InputObject <IConfluentIdentity> [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Perbarui Sumber daya Organisasi

## EXAMPLES

### Contoh 1: Perbarui organisasi dengan nama
```powershell
PS C:\> pdate-AzConfluentOrganization -ResourceGroupName azure-rg-test -Name confluentorg-02-pwsh -Tag @{"key01" = "value01"}

Location Name                 Type
-------- ----                 ----
eastus   confluentorg-02-pwsh Microsoft.Confluent/organizations
```

Perintah ini memperbarui organisasi terbatas menurut nama.

### Contoh 2: Perbarui organisasi terbatas menurut saluran
```powershell
PS C:\> Get-AzConfluentOrganization -ResourceGroupName azure-rg-test -Name confluentorg-02-pwsh | Update-AzConfluentOrganization -Tag @{"key01" = "value01"; "key02"="value02"}

Location Name                 Type
-------- ----                 ----
eastus   confluentorg-02-pwsh Microsoft.Confluent/organizations
```

Perintah ini memperbarui organisasi terbatas menurut saluran.

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Confluent.Models.IConfluentIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya organisasi

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: OrganizationName

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
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Microsoft Azure id langganan

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
Tag sumber daya ARM

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Confluent.Models.IConfluentIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Confluent.Models.Api20200301.IOrganizationResource

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IConfluentIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[OrganizationName <String>]`: Nama sumber daya organisasi
  - `[ResourceGroupName <String>]`: Nama grup sumber daya
  - `[SubscriptionId <String>]`: Microsoft Azure id langganan

## RELATED LINKS

