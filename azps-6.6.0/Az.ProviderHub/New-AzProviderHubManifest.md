---
external help file: ''
Module Name: Az.ProviderHub
online version: https://docs.microsoft.com/powershell/module/az.providerhub/new-azproviderhubmanifest
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubManifest.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/New-AzProviderHubManifest.md
ms.openlocfilehash: 3d8958e0d384de30b67185df0b9a741aed37b35d
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136156398"
---
# New-AzProviderHubManifest

## SYNOPSIS
Menghasilkan manifes untuk penyedia tertentu.

## SYNTAX

### Hasilkan (Default)
```
New-AzProviderHubManifest -ProviderNamespace <String> [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### GenerateViaIdentity
```
New-AzProviderHubManifest -InputObject <IProviderHubIdentity> [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghasilkan manifes untuk penyedia tertentu.

## EXAMPLES

### Contoh 1: Menghasilkan manifes penyedia sumber daya.
```powershell
PS C:\> New-AzProviderHubManifest -ProviderNamespace "Microsoft.Contoso"

Namespace         ProviderType     ProviderVersion RequiredFeature
---------         ------------     --------------- ---------------
Microsoft.Contoso Internal, Hidden 2.0
```

Buat manifes penyedia sumber daya.

### Contoh 2: Menghasilkan manifes penyedia sumber daya.
```powershell
PS C:\> New-AzProviderHubManifest -ProviderNamespace "Microsoft.Contoso"

Namespace         ProviderType     ProviderVersion RequiredFeature
---------         ------------     --------------- ---------------
Microsoft.Contoso Internal, Hidden 2.0
```

Buat manifes penyedia sumber daya.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.IProviderHubIdentity
Parameter Sets: GenerateViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProviderNamespace
Nama penyedia sumber daya yang dihosting dalam ProviderHub.

```yaml
Type: System.String
Parameter Sets: Generate
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
Parameter Sets: Generate
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.IProviderHubIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IResourceProviderFestfest

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IProviderHubIdentity> : Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[NestedResourceTypeFirst <String>]`: Tipe sumber daya anak pertama.
  - `[NestedResourceTypeSecond <String>]`: Tipe sumber daya anak kedua.
  - `[NestedResourceTypeThird <String>]`: Tipe sumber daya anak ketiga.
  - `[NotificationRegistrationName <String>]`: Pendaftaran pemberitahuan.
  - `[ProviderNamespace <String>]`: Nama penyedia sumber daya yang dihosting dalam ProviderHub.
  - `[ResourceType <String>]`: Tipe sumber daya.
  - `[RolloutName <String>]`: Nama peluncuran.
  - `[Sku <String>]`: SKU.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

