---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/get-azconnectednetworkdevice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Get-AzConnectedNetworkDevice.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Get-AzConnectedNetworkDevice.md
ms.openlocfilehash: e74687acb66d2ba25d92e987b4e6679a69d149f4
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146606244"
---
# Get-AzConnectedNetworkDevice

## SYNOPSIS
Mendapatkan informasi tentang perangkat yang ditentukan.

## SYNTAX

### Daftar (Default)
```
Get-AzConnectedNetworkDevice [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzConnectedNetworkDevice -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzConnectedNetworkDevice -InputObject <IConnectedNetworkIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar1
```
Get-AzConnectedNetworkDevice -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi tentang perangkat yang ditentukan.

## EXAMPLES

### Contoh 1: Get-AzConnectedNetworkDevice melalui Grup Sumber Daya dan Nama sumber daya
```powershell
PS C:\> Get-AzConnectedNetworkDevice -ResourceGroupName myResources -Name myMecDevice


DeviceType                   : AzureStackEdge
Id                           : /subscriptions/xxxxx-00000-xxxxx-00000/resourceGroups/myResources/providers/Microsoft.HybridNetwork/devices/myMecDevice
Location                     : westcentralus
Name                         : myMecDevice
NetworkFunction              : {/subscriptions/xxxxx-00000-xxxxx-00000/resourcegroups/myResources/providers/Microsoft.HybridNetwork/networkFunctions/myVnf1}
ProvisioningState            : Succeeded
ResourceGroupName            : myResources
Status                       : Registered
SystemDataCreatedAt          : 11/25/2020 5:34:49 AM
SystemDataCreatedBy          : user@microsoft.com
SystemDataCreatedByType      : User
SystemDataLastModifiedAt     : 11/25/2020 5:58:38 AM
SystemDataLastModifiedBy     : xxxxx-11111-xxxxx-11111
SystemDataLastModifiedByType : Application
Tag                          : Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20.TrackedResourceTags
Type                         : Microsoft.HybridNetwork/devices

```

Mendapatkan informasi tentang perangkat NFM di grup sumber daya myResources dengan nama myMecDevice.

### Contoh 2: Get-AzConnectedNetworkDevice melalui Identitas
```powershell
PS C:\> $mecDevice = @{ DeviceName = "myMecDevice1"; Location = "eastus"; ResourceGroupName = "myResources"; SubscriptionId = "xxxxx-00000-xxxxx-00000"}
PS C:\> Get-AzConnectedNetworkDevice -InputObject $mecDevice


DeviceType                   : AzureStackEdge
Id                           : /subscriptions/xxxxx-00000-xxxxx-00000/resourceGroups/myResources/providers/Microsoft.HybridNetwork/devices/myMecDevice1
Location                     : eastus
Name                         : myMecDevice1
NetworkFunction              : {/subscriptions/xxxxx-00000-xxxxx-00000/resourceGroups/mrg-vmware_sdwan_edge_zones-20211124063650/providers/Microsoft.HybridNetwork/networkFunctions/myEdge1}
ProvisioningState            : Succeeded
ResourceGroupName            : myResources
Status                       : Registered
SystemDataCreatedAt          : 11/23/2021 10:27:13 PM
SystemDataCreatedBy          : user@microsoft.com
SystemDataCreatedByType      : User
SystemDataLastModifiedAt     : 11/24/2021 7:42:41 AM
SystemDataLastModifiedBy     : xxxxx-11111-xxxxx-11111
SystemDataLastModifiedByType : Application
Tag                          : Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20.TrackedResourceTags
Type                         : microsoft.hybridnetwork/devices

```

Membuat identitas dengan nama perangkat myMecDevice1, grup sumber daya myResources, dan langganan tertentu.
Mendapatkan informasi tentang perangkat menggunakan identitas ini.

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
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.IConnectedNetworkIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama sumber daya perangkat.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: DeviceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: Get, List1
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
Parameter Sets: Get, List, List1
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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.IConnectedNetworkIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.IDevice

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IConnectedNetworkIdentity>`: Parameter Identitas
  - `[DeviceName <String>]`: Nama sumber daya perangkat.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[LocationName <String>]`: Wilayah Azure tempat sumber daya fungsi jaringan dibuat oleh pelanggan.
  - `[NetworkFunctionName <String>]`: Nama fungsi jaringan.
  - `[PreviewSubscription <String>]`: ID langganan pratinjau.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[RoleInstanceName <String>]`: Nama instans peran fungsi jaringan vendor.
  - `[ServiceKey <String>]`: GUID untuk fungsi jaringan vendor.
  - `[SkuName <String>]`: Nama sku.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VendorName <String>]`: Nama vendor.
  - `[VendorSkuName <String>]`: Nama sku fungsi jaringan.

## RELATED LINKS

