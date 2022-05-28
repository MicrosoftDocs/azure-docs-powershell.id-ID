---
external help file: ''
Module Name: Az.ConnectedMachine
online version: https://docs.microsoft.com/powershell/module/az.connectedmachine/update-azconnectedmachineextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/Update-AzConnectedMachineExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/Update-AzConnectedMachineExtension.md
ms.openlocfilehash: 775e8536c7624b4c6ba9383ee02a38a811cbfdd0
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145526383"
---
# Update-AzConnectedMachineExtension

## SYNOPSIS
Operasi untuk membuat atau memperbarui ekstensi.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzConnectedMachineExtension -MachineName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-AutoUpgradeMinorVersion] [-EnableAutomaticUpgrade] [-ForceRerun <String>]
 [-ProtectedSetting <IAny>] [-Publisher <String>] [-Setting <IAny>] [-Tag <Hashtable>] [-Type <String>]
 [-TypeHandlerVersion <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### Pembaruan
```
Update-AzConnectedMachineExtension -MachineName <String> -Name <String> -ResourceGroupName <String>
 -ExtensionParameter <IMachineExtensionUpdate> [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentity
```
Update-AzConnectedMachineExtension -InputObject <IConnectedMachineIdentity>
 -ExtensionParameter <IMachineExtensionUpdate> [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzConnectedMachineExtension -InputObject <IConnectedMachineIdentity> [-AutoUpgradeMinorVersion]
 [-EnableAutomaticUpgrade] [-ForceRerun <String>] [-ProtectedSetting <IAny>] [-Publisher <String>]
 [-Setting <IAny>] [-Tag <Hashtable>] [-Type <String>] [-TypeHandlerVersion <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk membuat atau memperbarui ekstensi.

## EXAMPLES

### Contoh 1: Memperbarui ekstensi
```powershell
$splat = @{
            ResourceGroupName = "connectedMachines"
            MachineName = "linux-eastus1_1"
            Name = "customScript"
            Settings = @{
                commandToExecute = "ls -l"
            }
        }
Update-AzConnectedMachineExtension @splat
```

```output
Name         Location ProvisioningState
----         -------- -----------------
customScript eastus   Succeeded
```

Memperbarui ekstensi pada komputer tertentu.

### Contoh 2: Memperbarui ekstensi dengan lokasi yang ditentukan melalui alur
```powershell
$extToUpdate = Get-AzConnectedMachineExtension -ResourceGroupName connectedMachines -MachineName linux-eastus1_1 -Name customScript
$extToUpdate | Update-AzConnectedMachineExtension -Settings @{
                commandToExecute = "ls -l"
            }
```

```output
Name         Location ProvisioningState
----         -------- -----------------
customScript eastus   Succeeded
```

Memperbarui ekstensi tertentu yang diteruskan melalui alur.
Di sini kita menggunakan ekstensi yang diteruskan melalui alur untuk membantu kita mengidentifikasi ekstensi mana yang ingin kita operasikan dan menentukan apa yang ingin kita ubah melalui parameter normal (seperti `-Settings`)

### Contoh 3: Memperbarui ekstensi dengan parameter ekstensi yang ditentukan melalui alur
```powershell
$extToUpdate = Get-AzConnectedMachineExtension -ResourceGroupName connectedMachines -MachineName linux-eastus1_1 -Name customScript
# Update the settings on the object that will be used via the pipeline
$extToUpdate.Setting.commandToExecute = "ls -l"
$splat = @{
            ResourceGroupName = "connectedMachines"
            MachineName = "linux-eastus1_1"
            Name = "customScript"
        }
$extToUpdate | Update-AzConnectedMachineExtension @splat
```

```output
Name         Location ProvisioningState
----         -------- -----------------
customScript eastus   Succeeded
```

Memperbarui ekstensi tertentu yang diteruskan melalui alur.
Di sini kita menggunakan ekstensi yang diteruskan melalui alur untuk memberikan perubahan yang ingin kita buat pada ekstensi.
Lokasi ekstensi tidak diambil melalui alur melainkan melalui parameter yang ditentukan secara normal (oleh parameter splat).

### Contoh 4: Menggunakan objek ekstensi sebagai lokasi dan parameter untuk memperbarui
```powershell
$extToUpdate = Get-AzConnectedMachineExtension -ResourceGroupName connectedMachines -MachineName linux-eastus1_1 -Name customScript
# Update the settings on the object that will be used via the pipeline
$extToUpdate.Setting.commandToExecute = "ls -l"
$extToUpdate | Update-AzConnectedMachineExtension -ExtensionParameter $extToUpdate
```

```output
Name         Location ProvisioningState
----         -------- -----------------
customScript eastus   Succeeded
```

Memperbarui ekstensi tertentu yang diteruskan melalui alur.
Di sini kami menggunakan ekstensi yang diteruskan melalui alur untuk membantu kami mengidentifikasi ekstensi mana yang ingin kami operasikan.
Selain itu, kami menggunakan parameter objek ekstensi untuk menentukan apa yang harus diperbarui.

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

### -AutoUpgradeMinorVersion
Menunjukkan apakah ekstensi harus menggunakan versi minor yang lebih baru jika tersedia pada waktu penyebaran.
Setelah disebarkan, bagaimanapun, ekstensi tidak akan meningkatkan versi kecil kecuali dipekerjakan kembali, bahkan jika properti ini diatur ke true.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UpdateExpanded, UpdateViaIdentityExpanded
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

### -EnableAutomaticUpgrade
Menunjukkan apakah ekstensi harus ditingkatkan secara otomatis oleh platform jika ada versi yang lebih baru yang tersedia.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UpdateExpanded, UpdateViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionParameter
Menjelaskan Pembaruan Ekstensi Mesin.
Untuk membuat, lihat bagian CATATAN untuk properti EXTENSIONPARAMETER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IMachineExtensionUpdate
Parameter Sets: Update, UpdateViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ForceRerun
Bagaimana handler ekstensi harus diperbarui meskipun konfigurasi ekstensi tidak berubah.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded, UpdateViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.IConnectedMachineIdentity
Parameter Sets: UpdateViaIdentity, UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MachineName
Nama komputer tempat ekstensi harus dibuat atau diperbarui.

```yaml
Type: System.String
Parameter Sets: Update, UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama ekstensi komputer.

```yaml
Type: System.String
Parameter Sets: Update, UpdateExpanded
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

### -ProtectedSetting
Ekstensi dapat berisi protectedSettings atau protectedSettingsFromKeyVault atau tidak ada pengaturan yang dilindungi sama sekali.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.IAny
Parameter Sets: UpdateExpanded, UpdateViaIdentityExpanded
Aliases: ProtectedSettings

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Publisher
Nama penerbit handler ekstensi.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded, UpdateViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: Update, UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Pengaturan
Pengaturan publik berformat Json untuk ekstensi.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.IAny
Parameter Sets: UpdateExpanded, UpdateViaIdentityExpanded
Aliases: Settings

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
Parameter Sets: Update, UpdateExpanded
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
Parameter Sets: UpdateExpanded, UpdateViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Menentukan jenis ekstensi; contohnya adalah "CustomScriptExtension".

```yaml
Type: System.String
Parameter Sets: UpdateExpanded, UpdateViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeHandlerVersion
Menentukan versi handler skrip.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded, UpdateViaIdentityExpanded
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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IMachineExtensionUpdate

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.IConnectedMachineIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IMachineExtension

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


EXTENSIONPARAMETER <IMachineExtensionUpdate>: Menjelaskan Pembaruan Ekstensi Mesin.
  - `[Tag <IResourceUpdateTags>]`: Tag sumber daya
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[AutoUpgradeMinorVersion <Boolean?>]`: Menunjukkan apakah ekstensi harus menggunakan versi minor yang lebih baru jika tersedia pada waktu penyebaran. Setelah disebarkan, bagaimanapun, ekstensi tidak akan meningkatkan versi kecil kecuali dipekerjakan kembali, bahkan jika properti ini diatur ke true.
  - `[EnableAutomaticUpgrade <Boolean?>]`: Menunjukkan apakah ekstensi harus ditingkatkan secara otomatis oleh platform jika ada versi yang lebih baru yang tersedia.
  - `[ForceUpdateTag <String>]`: Bagaimana handler ekstensi harus dipaksa untuk memperbarui meskipun konfigurasi ekstensi tidak berubah.
  - `[ProtectedSetting <IAny>]`: Ekstensi dapat berisi protectedSettings atau protectedSettingsFromKeyVault atau tidak ada pengaturan yang dilindungi sama sekali.
  - `[Publisher <String>]`: Nama penerbit handler ekstensi.
  - `[Setting <IAny>]`: Pengaturan publik berformat Json untuk ekstensi.
  - `[Type <String>]`: Menentukan jenis ekstensi; contohnya adalah "CustomScriptExtension".
  - `[TypeHandlerVersion <String>]`: Menentukan versi penangan skrip.

INPUTOBJECT <IConnectedMachineIdentity>: Parameter Identitas
  - `[ExtensionName <String>]`: Nama ekstensi komputer.
  - `[GroupName <String>]`: Nama sumber daya tautan privat.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Lokasi sumber daya target.
  - `[MachineName <String>]`: Nama komputer hibrid.
  - `[PrivateEndpointConnectionName <String>]`: Nama koneksi titik akhir privat.
  - `[PrivateLinkScopeId <String>]`: Id (Guid) sumber daya Azure Arc PrivateLinkScope.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar/kecil.
  - `[ScopeName <String>]`: Nama sumber daya Azure Arc PrivateLinkScope.
  - `[SubscriptionId <String>]`: ID langganan target.

## RELATED LINKS

