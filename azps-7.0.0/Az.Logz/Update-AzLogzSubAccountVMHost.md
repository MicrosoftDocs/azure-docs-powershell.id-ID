---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.logz/update-azlogzsubaccountvmhost
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Update-AzLogzSubAccountVMHost.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Update-AzLogzSubAccountVMHost.md
ms.openlocfilehash: 8ce172107035e149a55c24d93a0e0dda42294a1d
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136569951"
---
# Update-AzLogzSubAccountVMHost

## SYNOPSIS
Permintaan pengiriman untuk memperbarui koleksi ketika Logz.io telah diinstal pada VM untuk monitor tertentu.

## SYNTAX

```
Update-AzLogzSubAccountVMHost -MonitorName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-State <VMHostUpdateStates>] [-VMResource <IVMResources[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Permintaan pengiriman untuk memperbarui koleksi ketika Logz.io telah diinstal pada VM untuk monitor tertentu.

## EXAMPLES

### Contoh 1: Mengirim permintaan untuk memperbarui koleksi jika Logz.io telah diinstal pada VM untuk monitor sub akun logz
```powershell
PS C:\> $vmResource = New-AzLogzVMResourcesObject -AgentVersion '1.0' -Id '/SUBSCRIPTIONS/CE37D538-DFA3-49C3-B3CD-149B4B7DB48A/RESOURCEGROUPS/KOYTEST/PROVIDERS/MICROSOFT.COMPUTE/VIRTUALMACHINES/TEST-VM-1'
PS C:\> Update-AzLogzSubAccountVMHost -ResourceGroupName logz-rg-test -MonitorName pwsh-logz04 -Name logz-pwshsub01 -VMResource $vmResource -State 'Install'

AgentVersion Id
------------ --
1.0          /SUBSCRIPTIONS/CE37D538-DFA3-49C3-B3CD-149B4B7DB48A/RESOURCEGROUPS/KOYTEST/PROVIDERS/MICROSOFT.COMPUTE/VIRTUALMACHINES/TEST-VM-1
```

Perintah ini mengirimkan permintaan untuk memperbarui kumpulan jika Logz.io telah diinstal pada VM untuk monitor sub akun logz.

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

### -MonitorName
Memantau nama sumber daya

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

### -Nama
Nama sumber daya Sub Akun

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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

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

### -Negara Bagian
Menentukan status operasi - instal/ hapus.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Logz.Support.VMHostUpdateStates
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMResource
Permintaan operasi pembaruan host vm daftar.
Untuk membuat, lihat bagian CATATAN untuk properti VMRESOURCE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.IVMResources[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.IVMResources

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


VMRESOURCE <IVMResources[]>: Permintaan operasi pembaruan host vm daftar.
  - `[AgentVersion <String>]`: Versi agen Logz yang diinstal pada VM.
  - `[Id <String>]`: Permintaan operasi pembaruan host vm daftar.

## RELATED LINKS

