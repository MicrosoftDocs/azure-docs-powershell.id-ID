---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 56C7B6F5-C2AC-4C5A-8930-645374694CC3
online version: ''
schema: 2.0.0
ms.openlocfilehash: 33e0a54ccbeda6ab5b60fe2af805dc24989ede8e
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422452"
---
# Set-AzureVMSqlServerExtension

## SYNOPSIS
Mengatur ekstensi SQL Server Azure di komputer virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### EnableSqlServerExtension (Default)
```
Set-AzureVMSqlServerExtension [[-ReferenceName] <String>] [[-Version] <String>]
 [[-AutoPatchingSettings] <AutoPatchingSettings>] [[-AutoBackupSettings] <AutoBackupSettings>]
 [[-KeyVaultCredentialSettings] <KeyVaultCredentialSettings>] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### DisableSqlServerExtension
```
Set-AzureVMSqlServerExtension [[-ReferenceName] <String>] [[-Version] <String>] [-Disable] -VM <IPersistentVM>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

### UninstallSqlServerExtension
```
Set-AzureVMSqlServerExtension [[-ReferenceName] <String>] [[-Version] <String>] [-Uninstall]
 -VM <IPersistentVM> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureVMSqlServerExtension** mengatur ekstensi SQL Server Azure di komputer virtual.

## EXAMPLES

### Contoh 1: Mengatur pengaturan patching otomatis pada komputer virtual
```
PS C:\> Get-AzureVM -ServiceName "ServiceName" -Name "VMName" | Set-AzureVMSqlServerExtension -AutoPatchingSettings $APS | Update-AzureVM
```

Perintah ini mengatur pengaturan patching otomatis di komputer virtual Azure.

### Contoh 2: Mengatur pengaturan pencadangan otomatis di komputer virtual
```
PS C:\> Get-AzureVM -ServiceName "ServiceName" -Name "VMName" | Set-AzureVMSqlServerExtension -AutoBackupSettings $ABS | Update-AzureVM
```

Perintah ini mengatur pengaturan pencadangan otomatis di komputer virtual Azure.

### Contoh 3: Menonaktifkan SQL Server ekstensi pada komputer virtual
```
PS C:\> Get-AzureVM -ServiceName "Service" -Name "VMName" | Set-AzureVMSqlServerExtension -Disable
```

Perintah ini akan SQL Server ekstensi mesin virtual pada komputer virtual tertentu.

### Contoh 4: Menghapus SQL Server ekstensi pada komputer virtual tertentu
```
PS C:\> Get-AzureVM -ServiceName "Service" -Name "VMName" | Set-AzureVMSqlServerExtension -Uninstall
```

Perintah ini akan menghapus instalan SQL Server ekstensi mesin virtual pada komputer virtual bernama VMName.

## PARAMETERS

### -AutoBackupSettings
Menentukan pengaturan pencadangan SQL Server otomatis.

```yaml
Type: AutoBackupSettings
Parameter Sets: EnableSqlServerExtension
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AutoPatchingSettings
Menentukan pengaturan patch SQL Server otomatis.

```yaml
Type: AutoPatchingSettings
Parameter Sets: EnableSqlServerExtension
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Disable
Mengindikasikan bahwa cmdlet ini menonaktifkan status ekstensi.

```yaml
Type: SwitchParameter
Parameter Sets: DisableSqlServerExtension
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultCredentialSettings
Menentukan pengaturan kredensial penyimpanan kunci.

```yaml
Type: KeyVaultCredentialSettings
Parameter Sets: EnableSqlServerExtension
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReferenceName
Menentukan nama referensi dari SQL Server ekstensi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Uninstall
Menunjukkan bahwa cmdlet ini menghapus SQL Server ekstensi ekstensi dari komputer virtual.

```yaml
Type: SwitchParameter
Parameter Sets: UninstallSqlServerExtension
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Versi
Menentukan versi ekstensi SQL Server yang Get-AzureVMSqlServerExtension mengambil pengaturannya.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual persisten.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureVMSqlServerExtension](./Get-AzureVMSqlServerExtension.md)

[Remove-AzureVMSqlServerExtension](./Remove-AzureVMSqlServerExtension.md)


