---
external help file: ''
Module Name: Az.ConnectedMachine
online version: https://docs.microsoft.com/powershell/module/az.connectedmachine/set-azconnectedprivatelinkscope
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/Set-AzConnectedPrivateLinkScope.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/Set-AzConnectedPrivateLinkScope.md
ms.openlocfilehash: e3c520858c061f9324004dcda37469705a35be51
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145500664"
---
# Set-AzConnectedPrivateLinkScope

## SYNOPSIS
Membuat (atau memperbarui) Azure Arc PrivateLinkScope.
Catatan: Anda tidak dapat menentukan nilai yang berbeda untuk InstrumentationKey atau AppId dalam operasi Put.

## SYNTAX

### UpdateExpanded (Default)
```
Set-AzConnectedPrivateLinkScope -ResourceGroupName <String> -ScopeName <String> -Location <String>
 [-SubscriptionId <String>] [-PublicNetworkAccess <PublicNetworkAccessType>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Pembaruan
```
Set-AzConnectedPrivateLinkScope -ResourceGroupName <String> -ScopeName <String>
 -Parameter <IHybridComputePrivateLinkScope> [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat (atau memperbarui) Azure Arc PrivateLinkScope.
Catatan: Anda tidak dapat menentukan nilai yang berbeda untuk InstrumentationKey atau AppId dalam operasi Put.

## EXAMPLES

### Contoh 1: Mengatur cakupan tautan privat dalam langganan berdasarkan nama
```powershell
Set-AzConnectedPrivateLinkScope -ResourceGroupName $resourceGroupName -ScopeName $scopeName -PublicNetworkAccess "Disabled" -Tag $tags -Location $location
```

```output
Name         Location    PublicNetworkAccess ProvisioningState Tag
----         --------    ------------------- ----------------- ---
name         eastus2euap Disabled            Succeeded         Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.PrivateLinkScopesRes…
```

Memperbarui PublicNetworkAccess ke "Nonaktifkan" dan tag ke $tags

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

### -Lokasi
Lokasi sumber daya

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

### -Parameter
Definisi Azure Arc PrivateLinkScope.
Untuk membuat, lihat bagian CATATAN untuk properti PARAMETER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IHybridComputePrivateLinkScope
Parameter Sets: Update
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PublicNetworkAccess
Menunjukkan apakah komputer yang terkait dengan cakupan tautan privat juga dapat menggunakan titik akhir layanan Azure Arc publik.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Support.PublicNetworkAccessType
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

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

### -ScopeName
Nama sumber daya Azure Arc PrivateLinkScope.

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

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
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
Parameter Sets: UpdateExpanded
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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IHybridComputePrivateLinkScope

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IHybridComputePrivateLinkScope

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PARAMETER <IHybridComputePrivateLinkScope>: Definisi Azure Arc PrivateLinkScope.
  - `Location <String>`: Lokasi sumber daya
  - `[Tag <IPrivateLinkScopesResourceTags>]`: Tag sumber daya
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[PublicNetworkAccess <PublicNetworkAccessType?>]`: Menunjukkan apakah komputer yang terkait dengan cakupan tautan privat juga dapat menggunakan titik akhir layanan Azure Arc publik.
  - `[SystemDataCreatedAt <DateTime?>]`: Tanda waktu pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Jenis identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Tanda waktu modifikasi terakhir sumber daya (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir mengubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Jenis identitas yang terakhir memodifikasi sumber daya.

## RELATED LINKS

