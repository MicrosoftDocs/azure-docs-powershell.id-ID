---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.connectednetwork/remove-azconnectednetworkfunction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Remove-AzConnectedNetworkFunction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/Remove-AzConnectedNetworkFunction.md
ms.openlocfilehash: 17855e0aec6bf1465459295bb5a7669b5cbf14d5
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140001421"
---
# Remove-AzConnectedNetworkFunction

## SYNOPSIS
Menghapus sumber daya fungsi jaringan tertentu.
Operasi ini dapat memakan waktu hingga 1 jam untuk selesai.
Perilaku ini adalah perilaku layanan yang diharapkan.

## SYNTAX

### Hapus (Default)
```
Remove-AzConnectedNetworkFunction -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzConnectedNetworkFunction -InputObject <IConnectedNetworkIdentity> [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus sumber daya fungsi jaringan tertentu.
Operasi ini dapat memakan waktu hingga 1 jam untuk selesai.
Perilaku ini adalah perilaku layanan yang diharapkan.

## EXAMPLES

### Contoh 1: Remove-AzConnectedNetworkFunction melalui Grup Sumber Daya dan Nama sumber daya
```powershell
PS C:\> Remove-AzConnectedNetworkFunction -ResourceGroupName myResources -Name myVnf

```

Menghapus Fungsi Jaringan dalam Grup Sumber Daya sayaSumber dengan nama myVnf.

### Contoh 2: Remove-AzConnectedNetworkFunction melalui Identitas
```powershell
PS C:\> $vnf = Get-AzConnectedNetworkFunction -ResourceGroupName myResources -Name myVnf1
PS C:\> Remove-AzConnectedNetworkFunction -InputObject $vnf

```

Membuat identitas dengan nama myVnf1 dan nama grup sumber daya myResources.
Menghapus Fungsi Jaringan dengan Identitas tertentu.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -Nama
Nama fungsi jaringan.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: NetworkFunctionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: Delete
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
Parameter Sets: Delete
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.IConnectedNetworkIdentity

## OUTPUTS

### System.Boolean

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IConnectedNetworkIdentity>: Parameter Identitas
  - `[DeviceName <String>]`: Nama sumber daya perangkat.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[LocationName <String>]`: Kawasan Azure tempat sumber daya fungsi jaringan dibuat oleh pelanggan.
  - `[NetworkFunctionName <String>]`: Nama fungsi jaringan.
  - `[PreviewSubscription <String>]`: Mempratinjau ID langganan.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[RoleInstanceName <String>]`: Nama contoh peran dari fungsi jaringan vendor.
  - `[ServiceKey <String>]`: GUID untuk fungsi jaringan vendor.
  - `[SkuName <String>]`: Nama sku.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VendorName <String>]`: Nama vendor.
  - `[VendorSkuName <String>]`: Nama sku fungsi jaringan.

## RELATED LINKS

