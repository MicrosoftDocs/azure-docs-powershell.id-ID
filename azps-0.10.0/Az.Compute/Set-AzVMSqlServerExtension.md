---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help-Help.xml
Module Name: Az.Compute
ms.assetid: C650E465-7CDE-47F8-B85A-8FA3E1756FAF
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/set-azvmsqlserverextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Set-AzVMSqlServerExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Set-AzVMSqlServerExtension.md
ms.openlocfilehash: 1795216cbc18da2d503a1e0056d614337cd12785
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143265059"
---
# Set-AzVMSqlServerExtension

## SYNOPSIS
Mengatur ekstensi Server Azure SQL pada mesin virtual.

## SYNTAX

```
Set-AzVMSqlServerExtension [[-Version] <String>] [-ResourceGroupName] <String> [-VMName] <String>
 [[-Name] <String>] [[-AutoPatchingSettings] <AutoPatchingSettings>]
 [[-AutoBackupSettings] <AutoBackupSettings>] [[-KeyVaultCredentialSettings] <KeyVaultCredentialSettings>]
 [[-Location] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMSqlServerExtension** mengatur ekstensi AzureSQL Server pada mesin virtual.

## EXAMPLES

### Contoh 1: Mengatur pengaturan patch otomatis pada mesin virtual
```
PS C:\> $AutoPatchingConfig = New-AzureVMSqlServerAutoPatchingConfig -Enable -DayOfWeek "Thursday" -MaintenanceWindowStartingHour 11 -MaintenanceWindowDuration 120 -PatchCategory "Important"
PS C:\> Get-AzVM -ServiceName "Service02" -Name "VirtualMachine11" | Set-AzVMSqlServerExtension -AutoPatchingSettings $AutoPatchingConfig | Update-AzVM
```

Perintah pertama membuat objek konfigurasi menggunakan cmdlet **New-AzureVMSqlServerAutoPatchingConfig** .
Perintah menyimpan konfigurasi dalam variabel $AutoPatchingConfig.

Perintah kedua mendapatkan mesin virtual bernama VirtualMachine11 pada layanan bernama Service02 dengan menggunakan cmdlet Get-AzVM.
Perintah melewati objek tersebut ke cmdlet saat ini menggunakan operator pipeline.

Cmdlet saat ini mengatur pengaturan patch otomatis di $AutoPatchingConfig untuk mesin virtual.
Perintah melewati mesin virtual ke cmdlet Update-AzVM.

### Contoh 2: Mengatur pengaturan pencadangan otomatis pada mesin virtual
```
PS C:\> $AutoBackupConfig = New-AzureVMSqlServerAutoBackupConfig -Enable -RetentionPeriod 10 -StorageUri $StorageUrl -StorageKey $StorageAccountKeySecure
PS C:\> Get-AzVM -ServiceName "Service02" -Name "VirtualMachine11" | Set-AzVMSqlServerExtension -AutoBackupSettings $AutoBackupConfig | Update-AzVM
```

Perintah pertama membuat objek konfigurasi menggunakan cmdlet **New-AzureVMSqlServerAutoBackupConfig** .
Perintah menyimpan konfigurasi dalam variabel $AutoBackupConfig.

Perintah kedua mendapatkan mesin virtual bernama VirtualMachine11 pada layanan bernama Service02, lalu meneruskannya ke cmdlet saat ini.

Cmdlet saat ini mengatur pengaturan cadangan otomatis di $AutoBackupConfig untuk mesin virtual.
Perintah melewati mesin virtual ke cmdlet Update-AzVM.

### Contoh 3: Menonaktifkan ekstensi SQL Server di mesin virtual
```
PS C:\> Get-AzVM -ServiceName "Service03" -Name "VirtualMachine08" | Set-AzVMSqlServerExtension -Disable
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine08 di Service03, lalu mengirimkannya ke cmdlet saat ini.
Perintah menonaktifkan SQL Server ekstensi mesin virtual pada mesin virtual tersebut.

### Contoh 4: Menghapus instalan ekstensi SQL Server di mesin virtual tertentu
```
PS C:\> Get-AzVM -ServiceName "Service03" -Name "VirtualMachine08" | Set-AzVMSqlServerExtension -Uninstall
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine08 di Service03, lalu mengirimkannya ke cmdlet saat ini.
Perintah menghapus instalan SQL Server ekstensi mesin virtual pada mesin virtual tersebut.

## PARAMETERS

### -AutoBackupSettings
Menentukan setelan pencadangan SQL Server otomatis.
Untuk membuat objek **AutoBackupSettings** , gunakan cmdlet New-AzureVMSqlServerAutoBackupConfig.

```yaml
Type: AutoBackupSettings
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AutoPatchingSettings
Menentukan pengaturan patching SQL Server otomatis.
Untuk membuat objek **AutoPatchingSettings** , gunakan cmdlet New-AzureVMSqlServerAutoPatchingConfig.

```yaml
Type: AutoPatchingSettings
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultCredentialSettings
```yaml
Type: KeyVaultCredentialSettings
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi mesin maya.

```yaml
Type: String
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
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya mesin virtual.

```yaml
Type: String
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
Type: String
Parameter Sets: (All)
Aliases: HandlerVersion

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama mesin virtual tempat cmdlet ini mengatur ekstensi SQL Server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

## NOTES

## RELATED LINKS

[Get-AzVM](./Get-AzVM.md)

[Get-AzVMSqlServerExtension](./Get-AzVMSqlServerExtension.md)

[Baru-AzureVMSqlServerAutoPatchingConfig](./New-AzVMSqlServerAutoPatchingConfig.md)

[Baru-AzureVMSqlServerAutoBackupConfig](./New-AzVMSqlServerAutoBackupConfig.md)

[Remove-AzVMSqlServerExtension](./Remove-AzVMSqlServerExtension.md)

[Perbarui-AzVM](./Update-AzVM.md)


