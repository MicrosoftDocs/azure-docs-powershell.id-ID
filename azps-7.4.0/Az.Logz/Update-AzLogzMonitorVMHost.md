---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.logz/update-azlogzmonitorvmhost
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Update-AzLogzMonitorVMHost.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Update-AzLogzMonitorVMHost.md
ms.openlocfilehash: 21e714502867784cc2087c5b8802ed7405ef0a0e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142172983"
---
# Update-AzLogzMonitorVMHost

## SYNOPSIS
Mengirim permintaan untuk memperbarui pengumpulan ketika agen Logz.io telah diinstal di VM untuk monitor tertentu.

## SYNTAX

```
Update-AzLogzMonitorVMHost -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-State <VMHostUpdateStates>] [-VMResource <IVMResources[]>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mengirim permintaan untuk memperbarui pengumpulan ketika agen Logz.io telah diinstal di VM untuk monitor tertentu.

## EXAMPLES

### Contoh 1: Mengirim permintaan untuk memperbarui koleksi ketika agen Logz.io telah diinstal di VM untuk monitor tertentu
```powershell
$vmResource = New-AzLogzVMResourcesObject -AgentVersion '1.0' -Id '/SUBSCRIPTIONS/CE37D538-DFA3-49C3-B3CD-149B4B7DB48A/RESOURCEGROUPS/KOYTEST/PROVIDERS/MICROSOFT.COMPUTE/VIRTUALMACHINES/TEST-VM-1'
Update-AzLogzMonitorVMHost -ResourceGroupName logz-rg-test -Name pwsh-logz04 -State 'Install' -VMResource $vmResource
```

```output
AgentVersion Id
------------ --
1.0          /SUBSCRIPTIONS/CE37D538-DFA3-49C3-B3CD-149B4B7DB48A/RESOURCEGROUPS/KOYTEST/PROVIDERS/MICROSOFT.COMPUTE/VIRTUALMACHINES/TEST-VM-1
```

Perintah ini mengirim permintaan untuk memperbarui koleksi ketika agen Logz.io telah diinstal pada VM untuk monitor tertentu.

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

### -Nama
Pantau nama sumber daya

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
Nama ini tidak peka huruf besar kecil.

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
Permintaan daftar operasi pembaruan host vm.
Untuk membangun, lihat bagian CATATAN untuk properti VMRESOURCE dan membuat tabel hash.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.IVMResources

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


VMRESOURCE <IVMResources[]>: Permintaan operasi pembaruan host vm daftar.
  - `[AgentVersion <String>]`: Versi agen Logz yang diinstal di VM.
  - `[Id <String>]`: Permintaan daftar operasi pembaruan host vm.

## RELATED LINKS

