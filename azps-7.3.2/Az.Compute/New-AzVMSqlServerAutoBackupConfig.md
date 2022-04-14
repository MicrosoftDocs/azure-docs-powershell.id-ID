---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 0AC17275-17A9-47DE-BF04-C1A51DF057DC
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvmsqlserverautobackupconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMSqlServerAutoBackupConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMSqlServerAutoBackupConfig.md
ms.openlocfilehash: 81a88dcb75fd59f03b9a7953b53f7820dcfea03a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142115063"
---
# New-AzVMSqlServerAutoBackupConfig

## SYNOPSIS
Membuat objek konfigurasi untuk pencadangan otomatis SQL Server.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/new-azvmsqlserverautobackupconfig) untuk informasi terbaru.

## SYNTAX

### StorageUriSqlServerAutoBackup (Default)
```
New-AzVMSqlServerAutoBackupConfig [-ResourceGroupName] <String> [-Enable] [[-RetentionPeriodInDays] <Int32>]
 [-EnableEncryption] [[-CertificatePassword] <SecureString>] [[-StorageUri] <Uri>]
 [[-StorageKey] <SecureString>] [-BackupSystemDbs] [-BackupScheduleType <String>]
 [-FullBackupFrequency <String>] [-FullBackupStartHour <Int32>] [-FullBackupWindowInHours <Int32>]
 [-LogBackupFrequencyInMinutes <Int32>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### StorageContextSqlServerAutoBackup
```
New-AzVMSqlServerAutoBackupConfig [-ResourceGroupName] <String> [-Enable] [[-RetentionPeriodInDays] <Int32>]
 [-EnableEncryption] [[-CertificatePassword] <SecureString>] [[-StorageContext] <IStorageContext>]
 [[-StorageUri] <Uri>] [[-StorageKey] <SecureString>] [-BackupSystemDbs] [-BackupScheduleType <String>]
 [-FullBackupFrequency <String>] [-FullBackupStartHour <Int32>] [-FullBackupWindowInHours <Int32>]
 [-LogBackupFrequencyInMinutes <Int32>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVMSqlServerAutoBackupConfig** membuat objek konfigurasi untuk pencadangan otomatis SQL Server.

## EXAMPLES

### Contoh 1: Membuat konfigurasi cadangan otomatis menggunakan URI penyimpanan dan kunci akun
```powershell
$AutoBackupConfig = New-AzVMSqlServerAutoBackupConfig -Enable -RetentionPeriod 10 -StorageUri "\\contoso\StorageGeneral" -StorageKey "< Storage Key for ContosoGeneral >"
```

```output
Enable                : True
EnableEncryption      : False
RetentionPeriodInDays : 10
```

Perintah ini membuat objek konfigurasi cadangan otomatis dengan menentukan URI penyimpanan dan kunci akun.
Pencadangan otomatis diaktifkan dan pencadangan otomatis disimpan selama 10 hari.
Perintah menyimpan hasil dalam variabel $AutoBackupConfig.
Anda dapat menentukan item konfigurasi ini untuk cmdlet lain, seperti cmdlet Set-AzVMSqlServerExtension.

### Contoh 2: Membuat konfigurasi cadangan otomatis menggunakan konteks penyimpanan
```powershell
$StorageContext = New-AzStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral >"
$AutoBackupConfig = New-AzVMSqlServerAutoBackupConfig -StorageContext $StorageContext -Enable -RetentionPeriod 10
```

```output
Enable                : True
EnableEncryption      : False
RetentionPeriodInDays : 10
```

Perintah pertama membuat konteks penyimpanan, lalu menyimpannya dalam variabel $StorageContext.
Untuk informasi selengkapnya, lihat New-AzStorageContext.
Perintah kedua membuat objek konfigurasi cadangan otomatis dengan menentukan konteks penyimpanan dalam $StorageContext.
Pencadangan otomatis diaktifkan dan pencadangan otomatis disimpan selama 10 hari.

### Contoh 3: Membuat konfigurasi cadangan otomatis menggunakan konteks penyimpanan dengan enkripsi dan kata sandi
```powershell
$StorageContext = New-AzVMSqlServerAutoBackupConfig -StorageContext $StorageContext -Enable -RetentionPeriod 10 -EnableEncryption -CertificatePassword $CertificatePassword
```

```output
Enable                : True
EnableEncryption      : True
RetentionPeriodInDays : 10
```

Perintah ini membuat dan menyimpan objek konfigurasi cadangan otomatis.
Perintah menentukan konteks penyimpanan yang dibuat dalam contoh sebelumnya.
Perintah ini memungkinkan enkripsi dengan kata sandi.
Kata sandi sebelumnya disimpan sebagai string aman dalam variabel $CertificatePassword.
Untuk membuat string aman, gunakan cmdlet ConvertTo-SecureString.

## PARAMETERS

### -BackupScheduleType
Tipe jadwal cadangan, manual atau otomatis

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Manual, Automated

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackupSystemDbs
Database sistem cadangan

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificatePassword
Menentukan kata sandi untuk mengenkripsi sertifikat yang digunakan untuk melakukan pencadangan terenkripsi SQL Server.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Aktifkan
Menunjukkan bahwa cadangan otomatis untuk mesin virtual SQL Server diaktifkan.
Jika Anda menentukan parameter ini, cadangan otomatis mengatur jadwal cadangan untuk semua database saat ini dan baru.
Ini memperbarui pengaturan Pencadangan Terkelola Anda untuk mengikuti jadwal ini.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableEncryption
Menunjukkan bahwa cmdlet ini mengaktifkan enkripsi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FullBackupFrequency
Frekuensi Pencadangan Penuh Sql Server, harian atau mingguan

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Daily, Weekly

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FullBackupStartHour
Jam dalam sehari (0-23) ketika Pencadangan Penuh Sql Server harus dimulai

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FullBackupWindowInHours
Jendela Cadangan Penuh Sql Server dalam jam

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogBackupFrequencyInMinutes
Frekuensi Pencadangan Log Sql Server, sekali setiap 1-60 menit

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya mesin virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RetentionPeriodInDays
Menentukan jumlah hari untuk mempertahankan cadangan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageContext
Menentukan akun penyimpanan yang akan digunakan untuk menyimpan cadangan.
Untuk mendapatkan objek **AzureStorageContext** , gunakan cmdlet New-AzStorageContext.
Defaultnya adalah akun penyimpanan yang terkait dengan mesin virtual SQL Server.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: StorageContextSqlServerAutoBackup
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageKey
Menentukan kunci penyimpanan akun penyimpanan blob.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageUri
Menentukan Uniform Resource Identifier (URI) dari akun penyimpanan blob.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

### System.Int32

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

### System.Uri

### System.Security.SecureString

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.AutoBackupSettings

## CATATAN

## RELATED LINKS

[New-AzVMSqlServerAutoPatchingConfig](./New-AzVMSqlServerAutoPatchingConfig.md)

[Set-AzVMSqlServerExtension](./Set-AzVMSqlServerExtension.md)


