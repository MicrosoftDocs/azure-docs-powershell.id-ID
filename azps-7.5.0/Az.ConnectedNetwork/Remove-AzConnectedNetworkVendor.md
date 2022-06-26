---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/remove-azconnectednetworkvendor
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Remove-AzConnectedNetworkVendor.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Remove-AzConnectedNetworkVendor.md
ms.openlocfilehash: 1032599d51508bcef35062fd1a68108b1b5b51d5
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146624940"
---
# Remove-AzConnectedNetworkVendor

## SYNOPSIS
Menghapus vendor yang ditentukan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.connectednetwork/remove-azconnectednetworkvendor) untuk informasi terbaru.

## SYNTAX

### Hapus (Default)
```
Remove-AzConnectedNetworkVendor -Name <String> [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzConnectedNetworkVendor -InputObject <IConnectedNetworkIdentity> [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus vendor yang ditentukan.

## EXAMPLES

### Contoh 1: Remove-AzConnectedNetworkVendor melalui nama vendor
```powershell
PS C:\> Remove-AzConnectedNetworkVendor -Name MyVendor

```

Menghapus vendor dengan nama MyVendor

### Contoh 2: Remove-AzConnectedNetworkVendor melalui InputObject
```powershell
PS C:\> $vendor = Get-AzConnectedNetworkVendor -Name MyVendor1
PS C:\> Remove-AzConnectedNetworkVendor -InputObject $vendor

```

Menghapus vendor dengan nama MyVendor1

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
Parameter Sets: DeleteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama vendor.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: VendorName

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

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

