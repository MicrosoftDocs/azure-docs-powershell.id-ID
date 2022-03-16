---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: C650E465-7CDE-47F8-B85A-8FA3E1756FAF
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmsqlserverextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMSqlServerExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMSqlServerExtension.md
ms.openlocfilehash: d542c1779f038efef0b039936f695e2300e3be3b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140193319"
---
# Set-AzVMSqlServerExtension

## SYNOPSIS
Mengatur ekstensi SQL Server Azure di komputer virtual.

## SYNTAX

```
Set-AzVMSqlServerExtension [[-Version] <String>] [-ResourceGroupName] <String> [-VMName] <String>
 [[-Name] <String>] [[-AutoPatchingSettings] <AutoPatchingSettings>]
 [[-AutoBackupSettings] <AutoBackupSettings>] [[-KeyVaultCredentialSettings] <KeyVaultCredentialSettings>]
 [[-Location] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMSqlServerExtension** mengatur ekstensi AzureSQL Server di komputer virtual.

## EXAMPLES

### Contoh 1: Setel pengaturan patching otomatis pada komputer virtual
```powershell
$AutoPatchingConfig = New-AzVMSqlServerAutoPatchingConfig -Enable -DayOfWeek "Thursday" -MaintenanceWindowStartingHour 11 -MaintenanceWindowDuration 120 -PatchCategory "Important"
Get-AzVM -ServiceName "Service02" -Name "VirtualMachine11" | Set-AzVMSqlServerExtension -AutoPatchingSettings $AutoPatchingConfig | Update-AzVM
```

Perintah pertama membuat objek konfigurasi menggunakan cmdlet **New-AzVMSqlServerAutoPatchingConfig** .
Perintah menyimpan konfigurasi di $AutoPatchingConfig baru.
Perintah kedua mendapatkan mesin virtual bernama VirtualMachine11 di layanan yang bernama Service02 dengan menggunakan cmdlet Get-AzVM baru.
Perintah melewati objek itu ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet saat ini mengatur pengaturan patching otomatis $AutoPatchingConfig untuk mesin virtual.
Perintah melewati mesin virtual ke Update-AzVM cmdlet.

### Contoh 2: Mengatur pengaturan pencadangan otomatis di komputer virtual
```powershell
$AutoBackupConfig = New-AzVMSqlServerAutoBackupConfig -Enable -RetentionPeriod 10 -StorageUri $StorageUrl -StorageKey $StorageAccountKeySecure
Get-AzVM -ServiceName "Service02" -Name "VirtualMachine11" | Set-AzVMSqlServerExtension -AutoBackupSettings $AutoBackupConfig | Update-AzVM
```

Perintah pertama membuat objek konfigurasi dengan menggunakan cmdlet **New-AzVMSqlServerAutoBackupConfig** .
Perintah menyimpan konfigurasi di $AutoBackupConfig baru.
Perintah kedua mendapatkan mesin virtual bernama VirtualMachine11 di layanan yang bernama Service02, lalu meneruskannya ke cmdlet saat ini.
Cmdlet saat ini mengatur pengaturan pencadangan otomatis di $AutoBackupConfig untuk mesin virtual.
Perintah melewati mesin virtual ke Update-AzVM cmdlet.

### Contoh 3: Menonaktifkan SQL Server ekstensi pada komputer virtual
```powershell
Get-AzVM -ServiceName "Service03" -Name "VirtualMachine08" | Set-AzVMSqlServerExtension -Disable
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine08 di Service03, lalu meneruskannya ke cmdlet saat ini.
Perintah akan menonaktifkan SQL Server mesin virtual pada komputer virtual tersebut.

### Contoh 4: Menghapus SQL Server ekstensi pada komputer virtual tertentu
```powershell
Get-AzVM -ServiceName "Service03" -Name "VirtualMachine08" | Set-AzVMSqlServerExtension -Uninstall
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine08 di Service03, lalu meneruskannya ke cmdlet saat ini.
Perintah akan menghapus instalan SQL Server ekstensi mesin virtual tersebut di komputer virtual tersebut.

## PARAMETERS

### -AutoBackupSettings
Menentukan pengaturan pencadangan SQL Server otomatis.
Untuk membuat objek **AutoBackupSettings** , gunakan cmdlet New-AzVMSqlServerAutoBackupConfig cmdlet.

```yaml
Type: Microsoft.Azure.Commands.Compute.AutoBackupSettings
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AutoPatchingSettings
Menentukan pengaturan patch SQL Server otomatis.
Untuk membuat objek **AutoPatchingSettings** , gunakan cmdlet New-AzVMSqlServerAutoPatchingConfig cmdlet.

```yaml
Type: Microsoft.Azure.Commands.Compute.AutoPatchingSettings
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultCredentialSettings
```yaml
Type: Microsoft.Azure.Commands.Compute.KeyVaultCredentialSettings
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi mesin virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama SQL Server ekstensi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya komputer virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Versi
Menentukan versi ekstensi SQL Server.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: HandlerVersion

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama mesin virtual tempat cmdlet ini mengatur SQL Server ekstensi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Compute.AutoPatchingSettings

### Microsoft.Azure.Commands.Compute.AutoBackupSettings

### Microsoft.Azure.Commands.Compute.KeyVaultCredentialSettings

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

## CATATAN

## RELATED LINKS

[Get-azvm](./Get-AzVM.md)

[Get-AzVMSqlServerExtension](./Get-AzVMSqlServerExtension.md)

[New-azvmSqlServerAutoPatchingConfig](./New-AzVMSqlServerAutoPatchingConfig.md)

[New-azvmSqlServerAutoBackupConfig](./New-AzVMSqlServerAutoBackupConfig.md)

[Remove-AzVMSqlServerExtension](./Remove-AzVMSqlServerExtension.md)

[Update-azvm](./Update-AzVM.md)


