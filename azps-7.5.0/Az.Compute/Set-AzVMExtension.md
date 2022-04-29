---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 064196C3-ABF3-4F3A-A4AB-EB0D27098C70
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMExtension.md
ms.openlocfilehash: 6c884b600f0e22ea0ea6fa36f2e0bc46fafe7f02
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144232788"
---
# Set-AzVMExtension

## SYNOPSIS
Memperbarui properti ekstensi atau menambahkan ekstensi ke komputer virtual.

## SYNTAX

### Pengaturan (Default)
```
Set-AzVMExtension -Publisher <String> -ExtensionType <String> [-Settings <Hashtable>]
 [-ProtectedSettings <Hashtable>] [-EnableAutomaticUpgrade <Boolean>] [-AsJob] [-ResourceGroupName] <String>
 [-VMName] <String> -Name <String> [-TypeHandlerVersion <String>] [-Location <String>]
 [-DisableAutoUpgradeMinorVersion] [-ForceRerun <String>] [-NoWait] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SettingString
```
Set-AzVMExtension -Publisher <String> -ExtensionType <String> [-SettingString <String>]
 [-ProtectedSettingString <String>] [-EnableAutomaticUpgrade <Boolean>] [-AsJob] [-ResourceGroupName] <String>
 [-VMName] <String> -Name <String> [-TypeHandlerVersion <String>] [-Location <String>]
 [-DisableAutoUpgradeMinorVersion] [-ForceRerun <String>] [-NoWait] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMExtension** memperbarui properti untuk Ekstensi Komputer Virtual yang ada atau menambahkan ekstensi ke komputer virtual.

## EXAMPLES

### Contoh 1: Mengubah pengaturan dengan menggunakan tabel hash
```powershell
$Settings = @{"fileUris" = "[]"; "commandToExecute" = ""};
$ProtectedSettings = @{"storageAccountName" = $stoname; "storageAccountKey" = $stokey};
Set-AzVMExtension -ResourceGroupName "ResourceGroup11" -Location "West US" -VMName "VirtualMachine22" -Name "ContosoTest" -Publisher "Contoso.Compute" -ExtensionType "CustomScriptExtension" -TypeHandlerVersion "1.1" -Settings $Settings -ProtectedSettings $ProtectedSettings;
```

Dua perintah pertama menggunakan sintaks Windows PowerShell standar untuk membuat tabel hash, lalu menyimpan tabel hash tersebut di variabel $Pengaturan dan $ProtectedSettings.
Untuk informasi selengkapnya, ketik `Get-Help about_Hash_Tables`.
Perintah kedua mencakup dua nilai yang dibuat sebelumnya dan disimpan dalam variabel.
Perintah akhir memodifikasi ekstensi komputer virtual bernama VirtualMachine22 di ResourceGroup11 sesuai dengan konten $Pengaturan dan $ProtectedSettings.
Perintah menentukan informasi lain yang diperlukan yang menyertakan penerbit dan jenis ekstensi.

### Contoh 2: Mengubah pengaturan dengan menggunakan string
```powershell
$SettingsString = '{"fileUris":[],"commandToExecute":""}';
$ProtectedSettingsString = '{"storageAccountName":"' + $stoname + '","storageAccountKey":"' + $stokey + '"}';
Set-AzVMExtension -ResourceGroupName "ResourceGroup11" -Location "West US" -VMName "VirtualMachine22" -Name "CustomScriptExtension" -Publisher "Contoso.Compute" -ExtensionType "CustomScriptExtension" -TypeHandlerVersion "1.1" -SettingString $SettingsString -ProtectedSettingString $ProtectedSettingsString ;
```

Dua perintah pertama membuat string yang berisi pengaturan, lalu menyimpannya dalam variabel $SettingsString dan $ProtectedSettingsString.
Perintah akhir memodifikasi ekstensi komputer virtual bernama VirtualMachine22 di ResourceGroup11 sesuai dengan konten $SettingsString dan $ProtectedSettingsString.
Perintah menentukan informasi lain yang diperlukan yang menyertakan penerbit dan jenis ekstensi.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -DisableAutoUpgradeMinorVersion
Menunjukkan bahwa cmdlet ini mencegah agen tamu Azure memperbarui ekstensi secara otomatis ke versi minor yang lebih baru.
Secara default, cmdlet ini memungkinkan agen tamu memperbarui ekstensi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableAutomaticUpgrade
Menunjukkan apakah ekstensi harus ditingkatkan secara otomatis oleh platform jika ada versi ekstensi yang lebih baru yang tersedia.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtensionType
Menentukan jenis ekstensi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ForceRerun
Menunjukkan bahwa cmdlet ini memaksa pengoperasian ulang konfigurasi ekstensi yang sama pada komputer virtual tanpa menghapus instalan dan menginstal ulang ekstensi.
Nilainya bisa berupa string apa pun yang berbeda dari nilai saat ini.
Jika forceUpdateTag tidak diubah, pembaruan untuk pengaturan publik atau terproteksi masih diterapkan oleh handler.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi komputer virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Menentukan nama ekstensi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ExtensionName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoWait
Memulai operasi dan segera kembali, sebelum operasi selesai. Untuk menentukan apakah operasi telah berhasil diselesaikan, gunakan beberapa mekanisme lain.

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

### -ProtectedSettings
Menentukan konfigurasi privat untuk ekstensi, sebagai tabel hash.
Cmdlet ini mengenkripsi konfigurasi privat.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Settings
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProtectedSettingString
Menentukan konfigurasi privat untuk ekstensi, sebagai string.
Cmdlet ini mengenkripsi konfigurasi privat.

```yaml
Type: System.String
Parameter Sets: SettingString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publisher
Menentukan nama penerbit ekstensi.
Penerbit memberikan nama saat penerbit mendaftarkan ekstensi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
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
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pengaturan
Menentukan konfigurasi publik untuk ekstensi, sebagai tabel hash.
Cmdlet ini tidak mengenkripsi konfigurasi publik.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Settings
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SettingString
Menentukan konfigurasi publik untuk ekstensi, sebagai string.
Cmdlet ini tidak mengenkripsi konfigurasi publik.

```yaml
Type: System.String
Parameter Sets: SettingString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TypeHandlerVersion
Menentukan versi ekstensi yang akan digunakan untuk komputer virtual ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: HandlerVersion, Version

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName
Menentukan nama komputer virtual.
Cmdlet ini memodifikasi ekstensi untuk komputer virtual yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Collections.Hashtable

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

## NOTES

## RELATED LINKS

[Get-AzVMExtension](./Get-AzVMExtension.md)

[Remove-AzVMExtension](./Remove-AzVMExtension.md)


