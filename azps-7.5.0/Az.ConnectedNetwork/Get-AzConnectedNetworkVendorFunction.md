---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/get-azconnectednetworkvendorfunction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Get-AzConnectedNetworkVendorFunction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Get-AzConnectedNetworkVendorFunction.md
ms.openlocfilehash: adbc7bb3223b635cd9e9e8c2978f600fe2d720f6
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144212606"
---
# Get-AzConnectedNetworkVendorFunction

## SYNOPSIS
Mendapatkan informasi tentang fungsi jaringan vendor yang ditentukan.

## SYNTAX

### Daftar (Default)
```
Get-AzConnectedNetworkVendorFunction -LocationName <String> -VendorName <String> [-SubscriptionId <String[]>]
 [-Filter <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzConnectedNetworkVendorFunction -LocationName <String> -ServiceKey <String> -VendorName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzConnectedNetworkVendorFunction -InputObject <IConnectedNetworkIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi tentang fungsi jaringan vendor yang ditentukan.

## EXAMPLES

### Contoh 1: Get-AzConnectedNetworkVendorFunction melalui Nama Lokasi, Kunci Layanan, dan Langganan
```powershell
PS C:\> Get-AzConnectedNetworkVendorFunction -LocationName centraluseuap -ServiceKey 1234-abcd-4321-dcba -SubscriptionId xxxx-3333-xxxx-3333 -VendorName myVendor

Id                                 : /subscriptions/xxxx-3333-xxxx-3333/providers/Microsoft.HybridNetwork/locations/centraluseuap/vendors/myVendor/networkfunctions/1b69005b-9168-4d74-a371-d4c4f6a521d
                                     0
Name                               : 1234-abcd-4321-dcba
NetworkFunctionVendorConfiguration : {Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.SshPublicKey}
ProvisioningState                  : Succeeded
ResourceGroupName                  :
SkuName                            : mySku
SkuType                            : EvolvedPacketCore
SystemDataCreatedAt                : 11/25/2021 2:04:28 PM
SystemDataCreatedBy                : xxxxx-11111-xxxxx-11111
SystemDataCreatedByType            : Application
SystemDataLastModifiedAt           : 11/25/2021 2:04:28 PM
SystemDataLastModifiedBy           : xxxxx-11111-xxxxx-11111
SystemDataLastModifiedByType       : Application
Type                               : microsoft.hybridnetwork/locations/vendors/networkfunctions
VendorProvisioningState            : NotProvisioned

```

Mendapatkan informasi fungsi jaringan vendor dengan kunci layanan 1234-abcd-4321-dcba, nama vendor myVendor, centraluseuap lokasi, dan langganan.
Kunci layanan dapat diperoleh saat mendapatkan detail funcrtion jaringan atau saat membuat fungsi jaringan.

### Contoh 2: Get-AzConnectedNetworkVendorFunction melalui Identitas
```powershell
PS C:\> $vendorNF = @{ ServiceKey = "1234-abcd-4321-dcba"; VendorName = "myVendor"; LocationName = "centraluseuap"; SubscriptionId = "xxxx-3333-xxxx-3333"}
PS C:\> Get-AzConnectedNetworkVendorFunction -InputObject $vendorNF

Id                                 : /subscriptions/xxxx-3333-xxxx-3333/providers/Microsoft.HybridNetwork/locations/centraluseuap/vendors/myVendor/networkfunctions/1b69005b-9168-4d74-a371-d4c4f6a521d
                                     0
Name                               : 1234-abcd-4321-dcba
NetworkFunctionVendorConfiguration : {Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.SshPublicKey}
ProvisioningState                  : Succeeded
ResourceGroupName                  :
SkuName                            : mySku
SkuType                            : EvolvedPacketCore
SystemDataCreatedAt                : 11/25/2021 2:04:44 PM
SystemDataCreatedBy                : xxxxx-11111-xxxxx-11111
SystemDataCreatedByType            : Application
SystemDataLastModifiedAt           : 11/25/2021 2:36:28 PM
SystemDataLastModifiedBy           : xxxxx-11111-xxxxx-11111
SystemDataLastModifiedByType       : Application
Type                               : microsoft.hybridnetwork/locations/vendors/networkfunctions
VendorProvisioningState            : Provisioned

```

Membuat identitas dengan kunci layanan 1234-abcd-4321-dcba, nama vendor myVendor, centraluseuap lokasi, dan langganan.
Mendapatkan informasi fungsi jaringan vendor menggunakan identitas ini.

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

### -Filter
Filter yang akan diterapkan pada operasi.
Properti yang dapat Anda gunakan untuk eq (sama dengan) adalah: skuType, skuName, dan vendorProvisioningState.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -LocationName
Wilayah Azure tempat sumber daya fungsi jaringan dibuat oleh pelanggan.

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

### -ServiceKey
GUID untuk fungsi jaringan vendor.

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

### -VendorName
Nama vendor.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.IConnectedNetworkIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.IVendorNetworkFunction

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IConnectedNetworkIdentity>: Parameter Identitas
  - `[DeviceName <String>]`: Nama sumber daya perangkat.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[LocationName <String>]`: Wilayah Azure tempat sumber daya fungsi jaringan dibuat oleh pelanggan.
  - `[NetworkFunctionName <String>]`: Nama fungsi jaringan.
  - `[PreviewSubscription <String>]`: PRATINJAU ID langganan.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[RoleInstanceName <String>]`: Nama instans peran fungsi jaringan vendor.
  - `[ServiceKey <String>]`: GUID untuk fungsi jaringan vendor.
  - `[SkuName <String>]`: Nama sku.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VendorName <String>]`: Nama vendor.
  - `[VendorSkuName <String>]`: Nama sku fungsi jaringan.

## RELATED LINKS

