---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: C650E465-7CDE-47F8-B85A-8FA3E1756FAF
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/set-azurermvmsqlserverextension
schema: 2.0.0
ms.openlocfilehash: 2a1dbf5eea7f772a7819ed341a681adc24134225
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421993"
---
# Set-AzureRmVMSqlServerExtension

## SYNOPSIS
Mengatur ekstensi SQL Server Azure di komputer virtual.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmVMSqlServerExtension [[-Version] <String>] [-ResourceGroupName] <String> [-VMName] <String>
 [[-Name] <String>] [[-AutoPatchingSettings] <AutoPatchingSettings>]
 [[-AutoBackupSettings] <AutoBackupSettings>] [[-KeyVaultCredentialSettings] <KeyVaultCredentialSettings>]
 [[-Location] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmVMSqlServerExtension** mengatur ekstensi AzureSQL Server di komputer virtual.

## EXAMPLES

### Contoh 1: Setel pengaturan patching otomatis pada komputer virtual
```
PS C:\> $AutoPatchingConfig = New-AzureVMSqlServerAutoPatchingConfig -Enable -DayOfWeek "Thursday" -MaintenanceWindowStartingHour 11 -MaintenanceWindowDuration 120 -PatchCategory "Important"
PS C:\> Get-AzureRmVM -ServiceName "Service02" -Name "VirtualMachine11" | Set-AzureRmVMSqlServerExtension -AutoPatchingSettings $AutoPatchingConfig | Update-AzureRmVM
```

Perintah pertama membuat objek konfigurasi menggunakan cmdlet **New-AzureVMSqlServerAutoPatchingConfig.**
Perintah menyimpan konfigurasi di $AutoPatchingConfig lain.

Perintah kedua mendapatkan mesin virtual bernama VirtualMachine11 di layanan yang bernama Service02 menggunakan cmdlet Get-AzureRmVM baru.
Perintah melewati objek itu ke cmdlet saat ini dengan menggunakan operator pipeline.

Cmdlet saat ini mengatur pengaturan patching otomatis $AutoPatchingConfig untuk komputer virtual.
Perintah tersebut akan melewati mesin virtual ke Update-AzureRmVM cmdlet.

### Contoh 2: Mengatur pengaturan pencadangan otomatis di komputer virtual
```
PS C:\> $AutoBackupConfig = New-AzureVMSqlServerAutoBackupConfig -Enable -RetentionPeriod 10 -StorageUri $StorageUrl -StorageKey $StorageAccountKeySecure
PS C:\> Get-AzureRmVM -ServiceName "Service02" -Name "VirtualMachine11" | Set-AzureRmVMSqlServerExtension -AutoBackupSettings $AutoBackupConfig | Update-AzureRmVM
```

Perintah pertama membuat objek konfigurasi menggunakan cmdlet **New-AzureVMSqlServerAutoBackupConfig.**
Perintah menyimpan konfigurasi di $AutoBackupConfig baru.

Perintah kedua mendapatkan mesin virtual bernama VirtualMachine11 di layanan yang bernama Service02, lalu meneruskannya ke cmdlet saat ini.

Cmdlet saat ini mengatur pengaturan pencadangan otomatis di $AutoBackupConfig untuk mesin virtual.
Perintah tersebut akan melewati mesin virtual ke Update-AzureRmVM cmdlet.

### Contoh 3: Menonaktifkan SQL Server ekstensi di komputer virtual
```
PS C:\> Get-AzureRmVM -ServiceName "Service03" -Name "VirtualMachine08" | Set-AzureRmVMSqlServerExtension -Disable
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine08 di Service03, lalu meneruskannya ke cmdlet saat ini.
Perintah akan menonaktifkan SQL Server ekstensi mesin virtual pada komputer virtual tersebut.

### Contoh 4: Menghapus instalan SQL Server ekstensi di komputer virtual tertentu
```
PS C:\> Get-AzureRmVM -ServiceName "Service03" -Name "VirtualMachine08" | Set-AzureRmVMSqlServerExtension -Uninstall
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine08 di Service03, lalu meneruskannya ke cmdlet saat ini.
Perintah akan menghapus instalan SQL Server ekstensi mesin virtual tersebut di komputer virtual tersebut.

## PARAMETERS

### -AutoBackupSettings
Menentukan pengaturan pencadangan SQL Server otomatis.
Untuk membuat objek **AutoBackupSettings,** gunakan cmdlet New-AzureVMSqlServerAutoBackupConfig cmdlet.

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
Menentukan pengaturan patch SQL Server otomatis.
Untuk membuat objek **AutoPatchingSettings,** gunakan cmdlet New-AzureVMSqlServerAutoPatchingConfig cmdlet.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
Menentukan lokasi mesin virtual.

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
Menentukan nama grup sumber daya komputer virtual.

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
Menentukan nama mesin virtual tempat cmdlet ini mengatur SQL Server ekstensi.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

## CATATAN

## RELATED LINKS

[Get-AzureRmVM](./Get-AzureRmVM.md)

[Get-AzureRmVMSqlServerExtension](./Get-AzureRMVMSqlServerExtension.md)





[Remove-AzureRmVMSqlServerExtension](./Remove-AzureRMVMSqlServerExtension.md)

[Update-AzureRmVM](./Update-AzureRmVM.md)


