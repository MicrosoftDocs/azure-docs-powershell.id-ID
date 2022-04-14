---
external help file: ''
Module Name: Az.ConnectedMachine
online version: https://docs.microsoft.com/powershell/module/az.connectedmachine/set-azconnectedmachineextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/Set-AzConnectedMachineExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedMachine/help/Set-AzConnectedMachineExtension.md
ms.openlocfilehash: 3f181306e8c19cf3072df4341dd68f7aea28546d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141839936"
---
# Set-AzConnectedMachineExtension

## SYNOPSIS
Operasi untuk membuat atau memperbarui ekstensi.

## SYNTAX

### UpdateExpanded (Default)
```
Set-AzConnectedMachineExtension -MachineName <String> -Name <String> -ResourceGroupName <String>
 -Location <String> [-SubscriptionId <String>] [-AutoUpgradeMinorVersion] [-EnableAutomaticUpgrade]
 [-ExtensionType <String>] [-ForceRerun <String>] [-InstanceViewName <String>] [-InstanceViewType <String>]
 [-InstanceViewTypeHandlerVersion <String>] [-ProtectedSetting <IAny>] [-Publisher <String>] [-Setting <IAny>]
 [-StatusCode <String>] [-StatusDisplayStatus <String>] [-StatusLevel <StatusLevelTypes>]
 [-StatusMessage <String>] [-StatusTime <DateTime>] [-Tag <Hashtable>] [-TypeHandlerVersion <String>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Update
```
Set-AzConnectedMachineExtension -MachineName <String> -Name <String> -ResourceGroupName <String>
 -ExtensionParameter <IMachineExtension> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Operasi untuk membuat atau memperbarui ekstensi.

## EXAMPLES

### Contoh 1: Mengatur ekstensi di komputer
```powershell
$Settings = @{ "commandToExecute" = "powershell.exe -c Get-Process" }
Set-AzConnectedMachineExtension -Name custom -ResourceGroupName ContosoTest -MachineName win-eastus1 -Location eastus -Publisher "Microsoft.Compute" -TypeHandlerVersion 1.10 -Settings $Settings -ExtensionType CustomScriptExtension
```

```output
Name   Location ProvisioningState
----   -------- -----------------
custom eastus   Succeeded
```

Mengatur ekstensi pada mesin.

### Contoh 2: Atur ekstensi dengan parameter ekstensi yang ditentukan melalui pipeline
```powershell
$otherExtension = Get-AzConnectedMachineExtension -Name custom -ResourceGroupName ContosoTest -MachineName other
$otherExtension | Set-AzConnectedMachineExtension -Name custom -ResourceGroupName ContosoTest -MachineName important
```

```output
Name   Location ProvisioningState
----   -------- -----------------
custom eastus   Succeeded
```

Tindakan ini mengatur ekstensi dengan parameter ekstensi yang disediakan oleh objek yang dikirimkan melalui pipeline.
Ini bagus jika Anda ingin mengambil parameter satu mesin dan menerapkannya ke mesin lain.

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

### -AutoUpgradeMinorVersion
Menunjukkan apakah ekstensi harus menggunakan versi minor yang lebih baru jika tersedia pada waktu penyebaran.
Namun, setelah disebarkan, ekstensi tidak akan memutakhirkan versi minor kecuali jika dieploy ulang, bahkan dengan properti ini diatur ke true.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UpdateExpanded
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
Menunjukkan apakah ekstensi harus dimutakhirkan secara otomatis oleh platform jika tersedia versi yang lebih baru.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionParameter
Menjelaskan Ekstensi Mesin.
Untuk membangun, lihat bagian CATATAN untuk properti EXTENSIONPARAMETER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IMachineExtension
Parameter Sets: Update
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ExtensionType
Menentukan tipe ekstensi; contohnya adalah "CustomScriptExtension".

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceRerun
Bagaimana pengatur ekstensi harus dipaksa untuk memperbarui meskipun konfigurasi ekstensi belum berubah.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceViewName
Nama ekstensi mesin.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceViewType
Menentukan tipe ekstensi; contohnya adalah "CustomScriptExtension".

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceViewTypeHandlerVersion
Menentukan versi penanganan skrip.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi geografis tempat sumber daya berada

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MachineName
Nama mesin tempat ekstensi harus dibuat atau diperbarui.

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
Nama ekstensi mesin.

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
Ekstensi dapat berisi baik ProtectedSettings atau protectedSettingsFromKeyVault atau tidak ada pengaturan yang diproteksi sama sekali.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.IAny
Parameter Sets: UpdateExpanded
Aliases: ProtectedSettings

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Publisher
Nama penerbit penanganan ekstensi.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
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

### -Pengaturan
Json memformat pengaturan publik untuk ekstensi tersebut.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.IAny
Parameter Sets: UpdateExpanded
Aliases: Settings

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusCode
Kode status.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusDisplayStatus
Label pendek yang dapat dilokalkan untuk status tersebut.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusLevel
Kode tingkat.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Support.StatusLevelTypes
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusMessage
Pesan status mendetail, termasuk untuk pemberitahuan dan pesan kesalahan.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusTime
Waktu status.

```yaml
Type: System.DateTime
Parameter Sets: UpdateExpanded
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

### -Tag
Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeHandlerVersion
Menentukan versi penanganan skrip.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IMachineExtension

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedMachine.Models.Api20210520.IMachineExtension

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


EXTENSIONPARAMETER <IMachineExtension>: Menjelaskan Ekstensi Mesin.
  - `Location <String>`: Lokasi geografis tempat sumber daya tinggal
  - `[Tag <ITrackedResourceTags>]`: Tag sumber daya.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[AutoUpgradeMinorVersion <Boolean?>]`: Menunjukkan apakah ekstensi harus menggunakan versi minor yang lebih baru jika tersedia pada waktu penggunaan. Namun, setelah disebarkan, ekstensi tidak akan memutakhirkan versi minor kecuali jika dieploy ulang, bahkan dengan properti ini diatur ke true.
  - `[EnableAutomaticUpgrade <Boolean?>]`: Menunjukkan apakah ekstensi harus dimutakhirkan secara otomatis oleh platform jika tersedia versi yang lebih baru.
  - `[ForceUpdateTag <String>]`: Bagaimana penanganan ekstensi harus dipaksa untuk memperbarui meskipun konfigurasi ekstensi belum berubah.
  - `[InstanceViewName <String>]`: Nama ekstensi mesin.
  - `[InstanceViewType <String>]`: Menentukan tipe ekstensi; contohnya adalah "CustomScriptExtension".
  - `[InstanceViewTypeHandlerVersion <String>]`: Menentukan versi pengatur skrip.
  - `[MachineExtensionType <String>]`: Menentukan tipe ekstensi; contohnya adalah "CustomScriptExtension".
  - `[ProtectedSetting <IAny>]`: Ekstensi dapat berisi baik ProtectedSettings atau protectedSettingsFromKeyVault atau tidak ada pengaturan yang diproteksi sama sekali.
  - `[Publisher <String>]`: Nama penerbit pengatur ekstensi.
  - `[Setting <IAny>]`: Json memformat pengaturan publik untuk ekstensi.
  - `[StatusCode <String>]`: Kode status.
  - `[StatusDisplayStatus <String>]`: Label pendek yang dapat dilokalkan untuk status tersebut.
  - `[StatusLevel <StatusLevelTypes?>]`: Kode tingkat.
  - `[StatusMessage <String>]`: Pesan status mendetail, termasuk untuk pemberitahuan dan pesan kesalahan.
  - `[StatusTime <DateTime?>]`: Waktu status.
  - `[SystemDataCreatedAt <DateTime?>]`: Stempel waktu pembuatan sumber daya (UTC).
  - `[SystemDataCreatedBy <String>]`: Identitas yang membuat sumber daya.
  - `[SystemDataCreatedByType <CreatedByType?>]`: Tipe identitas yang membuat sumber daya.
  - `[SystemDataLastModifiedAt <DateTime?>]`: Cap waktu modifikasi terakhir sumber daya (UTC)
  - `[SystemDataLastModifiedBy <String>]`: Identitas yang terakhir mengubah sumber daya.
  - `[SystemDataLastModifiedByType <CreatedByType?>]`: Tipe identitas yang terakhir mengubah sumber daya.
  - `[TypeHandlerVersion <String>]`: Menentukan versi pengatur skrip.

## RELATED LINKS

