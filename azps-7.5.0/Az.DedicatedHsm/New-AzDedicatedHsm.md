---
external help file: ''
Module Name: Az.DedicatedHsm
online version: https://docs.microsoft.com/powershell/module/az.dedicatedhsm/new-azdedicatedhsm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DedicatedHsm/help/New-AzDedicatedHsm.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DedicatedHsm/help/New-AzDedicatedHsm.md
ms.openlocfilehash: 525177dd2bdd17a514ebe6946e511167e9c896b5
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144217883"
---
# New-AzDedicatedHsm

## SYNOPSIS
Membuat atau Memperbarui HSM khusus dalam langganan yang ditentukan.

## SYNTAX

```
New-AzDedicatedHsm -Name <String> -ResourceGroupName <String> -Location <String> [-SubscriptionId <String>]
 [-ManagementNetworkInterface <INetworkInterface[]>] [-ManagementSubnetId <String>]
 [-NetworkInterface <INetworkInterface[]>] [-Sku <SkuName>] [-StampId <String>] [-SubnetId <String>]
 [-Tag <Hashtable>] [-Zone <String[]>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat atau Memperbarui HSM khusus dalam langganan yang ditentukan.

## EXAMPLES

### Contoh 1: Membuat Dedicated HSM ke jaringan virtual yang ada
```powershell
New-AzDedicatedHsm -Name hsm-n7wfxi -ResourceGroupName dedicatedhsm-rg-n359cz -Location eastus -Sku "SafeNet Luna Network HSM A790" -StampId stamp1 -SubnetId "/subscriptions/xxxx-xxxx-xxx-xxx/resourceGroups/dedicatedhsm-rg-n359cz/providers/Microsoft.Network/virtualNetworks/vnetq30la9/subnets/hsmsubnet" -NetworkInterface @{PrivateIPAddress = '10.2.1.120' }
```

```output
Name       Provisioning State SKU                           Location
----       ------------------ ---                           --------
hsm-n7wfxi Succeeded          SafeNet Luna Network HSM A790 eastus
```

Perintah ini membuat Dedicated HSM ke dalam jaringan virtual yang ada.

**CATATAN:** Saat ini `New-AzDedicatedHsm` memiliki batasan bahwa ia kembali sebelum HSM sepenuhnya disediakan di Azure.
Oleh karena itu setelah membuat HSM baru, silakan kueri statusnya `Provisioning State` `Succeeded` oleh `Get-AzDedicatedHsm` dan pastikan sebelum menggunakannya.

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

### -Lokasi
Lokasi Azure yang didukung tempat HSM khusus harus dibuat.

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

### -ManagementNetworkInterface
Menentukan daftar Id sumber daya untuk antarmuka jaringan yang terkait dengan HSM khusus.
Untuk membuat, lihat bagian CATATAN untuk properti MANAGEMENTNETWORKINTERFACE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DedicatedHsm.Models.Api20211130.INetworkInterface[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementSubnetId
Id sumber daya ARM dalam bentuk /subscriptions/{SubscriptionId}/resourceGroups/{ResourceGroupName}/...

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama Hsm khusus

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

### -NetworkInterface
Menentukan daftar Id sumber daya untuk antarmuka jaringan yang terkait dengan HSM khusus.
Untuk membuat, lihat bagian NOTES untuk properti NETWORKINTERFACE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DedicatedHsm.Models.Api20211130.INetworkInterface[]
Parameter Sets: (All)
Aliases:

Required: False
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

### -ResourceGroupName
Nama Grup Sumber Daya tempat sumber daya berada.

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

### -Sku
SKU HSM khusus

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DedicatedHsm.Support.SkuName
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StampId
Bidang ini akan digunakan ketika RP tidak mendukung Zona ketersediaan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
Id sumber daya ARM dalam bentuk /subscriptions/{SubscriptionId}/resourceGroups/{ResourceGroupName}/...

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Info masuk langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zona
Zona Dedicated Hsm.

```yaml
Type: System.String[]
Parameter Sets: (All)
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DedicatedHsm.Models.Api20211130.IDedicatedHsm

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


MANAGEMENTNETWORKINTERFACE <INetworkInterface[]>: Menentukan daftar Id sumber daya untuk antarmuka jaringan yang terkait dengan HSM khusus.
  - `[PrivateIPAddress <String>]`: Alamat IP privat antarmuka

NETWORKINTERFACE <INetworkInterface[]>: Menentukan daftar Id sumber daya untuk antarmuka jaringan yang terkait dengan HSM khusus.
  - `[PrivateIPAddress <String>]`: Alamat IP privat antarmuka

## RELATED LINKS

