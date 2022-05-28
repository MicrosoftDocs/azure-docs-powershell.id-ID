---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/get-azconnectednetworkvendorsku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Get-AzConnectedNetworkVendorSku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Get-AzConnectedNetworkVendorSku.md
ms.openlocfilehash: 6665f450062e845ac492b75f2203b617a991cb08
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145516486"
---
# Get-AzConnectedNetworkVendorSku

## SYNOPSIS
Mendapatkan informasi tentang sku yang ditentukan.

## SYNTAX

### Daftar (Default)
```
Get-AzConnectedNetworkVendorSku -VendorName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzConnectedNetworkVendorSku -SkuName <String> -VendorName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzConnectedNetworkVendorSku -InputObject <IConnectedNetworkIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi tentang sku yang ditentukan.

## EXAMPLES

### Contoh 1: Get-AzConnectedNetworkVendorSku menggunakan Nama vendor dan Id Langganan
```powershell
PS C:\> Get-AzConnectedNetworkVendorSku -VendorName myVendor -SubscriptionId xxxxx-22222-xxxxx-22222

DeploymentMode                                          : PrivateEdgeZone
Id                                                      : /subscriptions/xxxxx-22222-xxxxx-22222/providers/Microsoft.HybridNetwork/vendors/myVendor/VendorSkus/mySku
ManagedApplicationParameter                             : Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.VendorSkuPropertiesFormatManagedApplicationParameters
ManagedApplicationTemplate                              : Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.VendorSkuPropertiesFormatManagedApplicationTemplate
Name                                                    : mySku
NetworkFunctionTemplateNetworkFunctionRoleConfiguration : {Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.SshPublicKey}
NetworkFunctionType                                     :
Preview                                                 : True
ProvisioningState                                       : Succeeded
ResourceGroupName                                       :
SkuType                                                 : EvolvedPacketCore
SystemDataCreatedAt                                     : 11/4/2020 3:35:33 PM
SystemDataCreatedBy                                     : user@microsoft.com
SystemDataCreatedByType                                 : User
SystemDataLastModifiedAt                                : 11/4/2020 3:43:58 PM
SystemDataLastModifiedBy                                : xxxxx-11111-xxxxx-11111
SystemDataLastModifiedByType                            : Application
Type                                                    : Microsoft.HybridNetwork/vendors/VendorSkus

DeploymentMode                                          : PrivateEdgeZone
Id                                                      : /subscriptions/xxxxx-22222-xxxxx-22222/providers/Microsoft.HybridNetwork/vendors/myVendor/vendorskus/mySku_1
ManagedApplicationParameter                             : Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.VendorSkuPropertiesFormatManagedApplicationParameters
ManagedApplicationTemplate                              : Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.VendorSkuPropertiesFormatManagedApplicationTemplate
Name                                                    : mySku_1
NetworkFunctionTemplateNetworkFunctionRoleConfiguration : {Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.SshPublicKey}
NetworkFunctionType                                     :
Preview                                                 : True
ProvisioningState                                       : Failed
ResourceGroupName                                       :
SkuType                                                 : EvolvedPacketCore
SystemDataCreatedAt                                     : 11/11/2020 2:25:32 PM
SystemDataCreatedBy                                     : user@microsoft.com
SystemDataCreatedByType                                 : User
SystemDataLastModifiedAt                                : 11/11/2020 2:25:32 PM
SystemDataLastModifiedBy                                : user@microsoft.com
SystemDataLastModifiedByType                            : User
Type                                                    : Microsoft.HybridNetwork/vendors/vendorskus
```

Mengambil semua sku vendor myVendor dalam langganan yang diberikan.

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

### -SkuName
Nama sku.

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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.IVendorSku

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IConnectedNetworkIdentity>: Parameter Identitas
  - `[DeviceName <String>]`: Nama sumber daya perangkat.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[LocationName <String>]`: Wilayah Azure tempat sumber daya fungsi jaringan dibuat oleh pelanggan.
  - `[NetworkFunctionName <String>]`: Nama fungsi jaringan.
  - `[PreviewSubscription <String>]`: ID langganan pratinjau.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar/kecil.
  - `[RoleInstanceName <String>]`: Nama instans peran fungsi jaringan vendor.
  - `[ServiceKey <String>]`: GUID untuk fungsi jaringan vendor.
  - `[SkuName <String>]`: Nama sku.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VendorName <String>]`: Nama vendor.
  - `[VendorSkuName <String>]`: Nama sku fungsi jaringan.

## RELATED LINKS

