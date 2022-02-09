---
external help file: ''
Module Name: Az.ConnectedMachine
online version: https://docs.microsoft.com/powershell/module/az.connectedmachine/new-azconnectedprivatelinkscope
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/New-AzConnectedPrivateLinkScope.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/New-AzConnectedPrivateLinkScope.md
ms.openlocfilehash: bf6a0f932ff9c9d5fb66488eaa52fe9283c508dd
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138276284"
---
# New-AzConnectedPrivateLinkScope

## SYNOPSIS
Membuat (atau memperbarui) Azure Arc PrivateLinkScope.
Catatan: Anda tidak dapat menentukan nilai yang berbeda untuk InstrumentationKey maupun AppId dalam operasi Letakkan.

## SYNTAX

### CreateExpanded (Default)
```
New-AzConnectedPrivateLinkScope -ResourceGroupName <String> -ScopeName <String> -Location <String>
 [-SubscriptionId <String>] [-PublicNetworkAccess <PublicNetworkAccessType>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Buat
```
New-AzConnectedPrivateLinkScope -ResourceGroupName <String> -ScopeName <String>
 -Parameter <IHybridComputePrivateLinkScope> [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### CreateViaIdentity
```
New-AzConnectedPrivateLinkScope -InputObject <IConnectedMachineIdentity>
 -Parameter <IHybridComputePrivateLinkScope> [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### CreateViaIdentityExpanded
```
New-AzConnectedPrivateLinkScope -InputObject <IConnectedMachineIdentity> -Location <String>
 [-PublicNetworkAccess <PublicNetworkAccessType>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat (atau memperbarui) Azure Arc PrivateLinkScope.
Catatan: Anda tidak dapat menentukan nilai yang berbeda untuk InstrumentationKey maupun AppId dalam operasi Letakkan.

## EXAMPLES

### Contoh 1: Tambahkan lingkup link privat baru dalam langganan
```powershell
PS C:\> New-AzConnectedPrivateLinkScope -ResourceGroupName $resourceGroupName -ScopeName $scopeName -PublicNetworkAccess "Enabled" -Location $location

Name        Location    PublicNetworkAccess ProvisioningState Tag
----        --------    ------------------- ----------------- ---
name1      eastus2euap Enabled             Succeeded         Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.PrivateLinkScopesReso…

```

PublicNetworkAccess harus "Diaktifkan" atau "Dinonaktifkan"

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
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.IConnectedMachineIdentity
Parameter Sets: CreateViaIdentity, CreateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya

```yaml
Type: System.String
Parameter Sets: CreateExpanded, CreateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameter
Definisi Azure Arc PrivateLinkScope.
Untuk membuat, lihat bagian CATATAN untuk properti PARAMETER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IHybridComputePrivateLinkScope
Parameter Sets: Create, CreateViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PublicNetworkAccess
Menunjukkan apakah komputer yang terkait dengan lingkup tautan pribadi juga dapat menggunakan titik akhir layanan Azure Arc publik.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Support.PublicNetworkAccessType
Parameter Sets: CreateExpanded, CreateViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: Create, CreateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScopeName
Nama sumber daya Azure Arc PrivateLinkScope.

```yaml
Type: System.String
Parameter Sets: Create, CreateExpanded
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
Parameter Sets: Create, CreateExpanded
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
Parameter Sets: CreateExpanded, CreateViaIdentityExpanded
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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IHybridComputePrivateLinkScope

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.IConnectedMachineIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IHybridComputePrivateLinkScope

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IConnectedMachineIdentity>: Parameter Identitas
  - `[ExtensionName <String>]`: Nama ekstensi komputer.
  - `[GroupName <String>]`: Nama sumber daya tautan privat.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Lokasi sumber daya target.
  - `[MachineName <String>]`: Nama mesin hibrid.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[PrivateLinkScopeId <String>]`: Id (Guid) sumber daya Azure Arc PrivateLinkScope.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[ScopeName <String>]`: Nama sumber daya Azure Arc PrivateLinkScope.
  - `[SubscriptionId <String>]`: ID langganan target.

PARAMETER <IHybridComputePrivateLinkScope>: Definisi Azure Arc PrivateLinkScope.
  - `Location <String>`: Lokasi sumber daya
  - `[Tag <IPrivateLinkScopesResourceTags>]`: Tag sumber daya
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[PublicNetworkAccess <PublicNetworkAccessType?>]`: Menunjukkan apakah komputer yang terkait dengan lingkup tautan pribadi juga dapat menggunakan titik akhir layanan Azure Arc publik.
  - `[SystemDataCreatedAt <DateTime?>]`: Timestamp pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Tipe identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Timestamp sumber daya modifikasi terakhir (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir diubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Tipe identitas yang terakhir diubah sumber daya.

## RELATED LINKS

