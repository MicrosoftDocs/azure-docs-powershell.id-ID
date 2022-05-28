---
external help file: ''
Module Name: Az.ProviderHub
online version: https://docs.microsoft.com/powershell/module/az.providerhub/get-azproviderhubresourcetyperegistration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/Get-AzProviderHubResourceTypeRegistration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ProviderHub/help/Get-AzProviderHubResourceTypeRegistration.md
ms.openlocfilehash: fcec59bab8c8f898c5f4d3ec4a07dc06f61bc2b8
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145545925"
---
# Get-AzProviderHubResourceTypeRegistration

## SYNOPSIS
Mendapatkan detail jenis sumber daya di langganan dan penyedia yang diberikan.

## SYNTAX

### Daftar (Default)
```
Get-AzProviderHubResourceTypeRegistration -ProviderNamespace <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzProviderHubResourceTypeRegistration -ProviderNamespace <String> -ResourceType <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzProviderHubResourceTypeRegistration -InputObject <IProviderHubIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail jenis sumber daya di langganan dan penyedia yang diberikan.

## EXAMPLES

### Contoh 1: Cantumkan semua jenis sumber daya di bawah namespace layanan penyedia sumber daya.
```powershell
Get-AzProviderHubResourceTypeRegistration -ProviderNamespace "Microsoft.Contoso"
```

```output
Name                        Type
----                        ----
testResourceType1           Microsoft.ProviderHub/providerRegistrations/resourceTypeRegistrations
testResourceType2           Microsoft.ProviderHub/providerRegistrations/resourceTypeRegistrations
```

Cantumkan semua jenis sumber daya di bawah namespace layanan penyedia sumber daya.

### Contoh 2: Mendapatkan jenis sumber daya berdasarkan nama.
```powershell
Get-AzProviderHubResourceTypeRegistration -ProviderNamespace "Microsoft.Contoso" -ResourceType "testResourceType1"
```

```output
Name                        Type
----                        ----
testResourceType1           Microsoft.ProviderHub/providerRegistrations/resourceTypeRegistrations
```

Mendapatkan jenis sumber daya berdasarkan nama.

### Contoh 3: Mendapatkan jenis sumber daya berlapis menurut nama.
```powershell
Get-AzProviderHubResourceTypeRegistration -ProviderNamespace "Microsoft.Contoso" -ResourceType "testResourceType1/nestedResourceType"
```

```output
Name                                      Type
----                                      ----
testResourceType1/nestedResourceType      Microsoft.ProviderHub/providerRegistrations/resourceTypeRegistrations
```

Mendapatkan jenis sumber daya berdasarkan nama.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.IProviderHubIdentity
Parameter Sets: GetViaIdentity
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
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceType
Jenis sumber daya.

```yaml
Type: System.String
Parameter Sets: Get
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
Type: System.String[]
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.IProviderHubIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ProviderHub.Models.Api20201120.IResourceTypeRegistration

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IProviderHubIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[NestedResourceTypeFirst <String>]`: Jenis sumber daya anak pertama.
  - `[NestedResourceTypeSecond <String>]`: Jenis sumber daya anak kedua.
  - `[NestedResourceTypeThird <String>]`: Jenis sumber daya anak ketiga.
  - `[NotificationRegistrationName <String>]`: Pendaftaran pemberitahuan.
  - `[ProviderNamespace <String>]`: Nama penyedia sumber daya yang dihosting dalam ProviderHub.
  - `[ResourceType <String>]`: Jenis sumber daya.
  - `[RolloutName <String>]`: Nama peluncuran.
  - `[Sku <String>]`: SKU.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

