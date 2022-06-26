---
external help file: ''
Module Name: Az.ConnectedMachine
online version: https://docs.microsoft.com/powershell/module/az.connectedmachine/update-azconnectedextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/Update-AzConnectedExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/Update-AzConnectedExtension.md
ms.openlocfilehash: b56dd5d831aefaa0e3abcd1ccbc80ba4405a5f2d
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146601924"
---
# Update-AzConnectedExtension

## SYNOPSIS
Operasi untuk Meningkatkan Ekstensi Mesin.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.connectedmachine/update-azconnectedextension) untuk informasi terbaru.

## SYNTAX

### UpgradeExpanded (Default)
```
Update-AzConnectedExtension -MachineName <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-ExtensionTarget <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### Mutakhirkan
```
Update-AzConnectedExtension -MachineName <String> -ResourceGroupName <String>
 -ExtensionUpgradeParameter <IMachineExtensionUpgrade> [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpgradeViaIdentity
```
Update-AzConnectedExtension -InputObject <IConnectedMachineIdentity>
 -ExtensionUpgradeParameter <IMachineExtensionUpgrade> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpgradeViaIdentityExpanded
```
Update-AzConnectedExtension -InputObject <IConnectedMachineIdentity> [-ExtensionTarget <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk Meningkatkan Ekstensi Mesin.

## EXAMPLES

### Contoh 1: Memperbarui ekstensi di komputer ke versi tertentu
```powershell
$target = @{"Microsoft.Compute.CustomScriptExtension" = @{"targetVersion"="1.10.12"}}
Update-AzConnectedExtension -ResourceGroupName $env.ResourceGroupName -MachineName $machineName -ExtensionTarget $target
```

```output
<None>
```

Memperbarui ekstensi di komputer ke versi tertentu

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

### -ExtensionTarget
Menjelaskan Properti Target Ekstensi.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: UpgradeExpanded, UpgradeViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionUpgradeParameter
Menjelaskan Properti Peningkatan Ekstensi Mesin Untuk membangun, lihat bagian CATATAN untuk properti EXTENSIONUPGRADEPARAMETER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IMachineExtensionUpgrade
Parameter Sets: Upgrade, UpgradeViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.IConnectedMachineIdentity
Parameter Sets: UpgradeViaIdentity, UpgradeViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MachineName
Nama mesin hibrid.

```yaml
Type: System.String
Parameter Sets: Upgrade, UpgradeExpanded
Aliases:

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

### -ResourceGroupName
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: Upgrade, UpgradeExpanded
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
Parameter Sets: Upgrade, UpgradeExpanded
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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IMachineExtensionUpgrade

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.IConnectedMachineIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


EXTENSIONUPGRADEPARAMETER `<IMachineExtensionUpgrade>`: Menjelaskan Properti Peningkatan Ekstensi Mesin
  - `[ExtensionTarget <IExtensionTarget>]`: Menjelaskan Properti Target Ekstensi.
    - `[(Any) <IExtensionTargetProperties>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

INPUTOBJECT `<IConnectedMachineIdentity>`: Parameter Identitas
  - `[ExtensionName <String>]`: Nama ekstensi komputer.
  - `[GroupName <String>]`: Nama sumber daya tautan privat.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Lokasi sumber daya target.
  - `[MachineName <String>]`: Nama komputer hibrid.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[PrivateLinkScopeId <String>]`: Id (Guid) sumber daya Azure Arc PrivateLinkScope.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[ScopeName <String>]`: Nama sumber daya Azure Arc PrivateLinkScope.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

