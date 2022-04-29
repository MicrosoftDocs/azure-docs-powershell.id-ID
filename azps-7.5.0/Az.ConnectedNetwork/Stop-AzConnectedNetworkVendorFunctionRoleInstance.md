---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/stop-azconnectednetworkvendorfunctionroleinstance
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Stop-AzConnectedNetworkVendorFunctionRoleInstance.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Stop-AzConnectedNetworkVendorFunctionRoleInstance.md
ms.openlocfilehash: 8305681072f05f3786de3320a4d42543030442d2
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144219590"
---
# Stop-AzConnectedNetworkVendorFunctionRoleInstance

## SYNOPSIS
Mematikan (menghentikan) instans peran fungsi jaringan vendor.

## SYNTAX

### Hentikan (Default)
```
Stop-AzConnectedNetworkVendorFunctionRoleInstance -LocationName <String> -Name <String> -ServiceKey <String>
 -VendorName <String> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### StopViaIdentity
```
Stop-AzConnectedNetworkVendorFunctionRoleInstance -InputObject <IConnectedNetworkIdentity>
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mematikan (menghentikan) instans peran fungsi jaringan vendor.

## EXAMPLES

### Contoh 1: Stop-AzConnectedNetworkVendorFunctionRoleInstance melalui lokasi, serviceKey, nama vendor, dan nama instans peran
```powershell
PS C:\> Stop-AzConnectedNetworkVendorFunctionRoleInstance -LocationName centraluseuap -ServiceKey 1234-abcd-4321-dcba -SubscriptionId xxxx-3333-xxxx-3333 -VendorName myVendor -Name role1

```

Menghentikan instans peran fungsi jaringan vendor dengan serviceKey yang ditentukan, centraluseuap lokasi, nama vendor myVendor, dan peran nama instans peran1.

### Contoh 2: Stop-AzConnectedNetworkVendorFunctionRoleInstance melalui Identitas
```powershell
PS C:\> $role = @{ RoleInstanceName = "role1"; LocationName = "centraluseuap"; SubscriptionId = "xxxx-3333-xxxx-3333"; VendorName = "myVendor"; serviceKey = "1234-abcd-4321-dcba"}
PS C:\> Stop-AzConnectedNetworkVendorFunctionRoleInstance -InputObject $role

```

Membuat identitas dengan peran nama instans peran1, centraluseuap lokasi, nama vendor myVendor langganan yang ditentukan, serviceKey.
Menghentikan instans peran dengan identitas yang diberikan.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Parameter Sets: StopViaIdentity
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
Parameter Sets: Stop
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama instans peran fungsi jaringan vendor.

```yaml
Type: System.String
Parameter Sets: Stop
Aliases: RoleInstanceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceKey
GUID untuk fungsi jaringan vendor.

```yaml
Type: System.String
Parameter Sets: Stop
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
Parameter Sets: Stop
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
Parameter Sets: Stop
Aliases:

Required: True
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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.IConnectedNetworkIdentity

## OUTPUTS

### System.Boolean

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

