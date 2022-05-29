---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: D93666EC-C252-4E3B-B311-50B6EEA6D4BF
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmaccessextension
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMAccessExtension.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMAccessExtension.md
ms.openlocfilehash: 0930f75a49131b5b1ccd882d9d1e0454e624aa45
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145733014"
---
# Set-AzVMAccessExtension

## SYNOPSIS
Menambahkan ekstensi VMAccess ke komputer virtual.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/set-azvmaccessextension) untuk informasi terbaru.

## SYNTAX

```
Set-AzVMAccessExtension [-Credential <PSCredential>] [-ResourceGroupName] <String> [-VMName] <String>
 -Name <String> [-TypeHandlerVersion <String>] [-Location <String>] [-DisableAutoUpgradeMinorVersion]
 [-ForceRerun <String>] [-NoWait] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMAccessExtension** menambahkan Ekstensi VMAccess Komputer Virtual Akses Komputer Virtual (VMAccess) Virtual Machine ke komputer virtual. Ekstensi VMAccess dapat digunakan untuk mengatur kata sandi sementara dan ini harus segera diubah setelah masuk ke komputer. Ini tidak didukung pada Pengendali Domain Windows.

## EXAMPLES

### Contoh 1: Menambahkan ekstensi VMAccess
```powershell
Set-AzVMAccessExtension -ResourceGroupName "ResourceGroup11" -Location "Central US" -VMName "VirtualMachine07" -Name "ContosoTest" -TypeHandlerVersion "2.4"
```

Perintah ini menambahkan ekstensi VMAccess untuk komputer virtual bernama VirtualMachine07 di ResourceGroup11.
Perintah menentukan nama dan versi handler jenis untuk VMAccess.

### Contoh 2

Menambahkan ekstensi VMAccess ke komputer virtual. (dibuat otomatis)

```powershell
<!-- Aladdin Generated Example --> 
Set-AzVMAccessExtension -Credential <PSCredential> -Location 'Central US' -Name 'ContosoTest' -ResourceGroupName 'ResourceGroup11' -TypeHandlerVersion '2.4' -VMName 'VirtualMachine07'
```

## PARAMETERS

### -Credential
Menentukan nama pengguna dan kata sandi untuk komputer virtual sebagai objek **PSCredential** .
Jika Anda mengetikkan nama yang berbeda dari akun administrator lokal saat ini di VM Anda, ekstensi VMAccess akan menambahkan akun administrator lokal dengan nama tersebut, dan menetapkan kata sandi yang Anda tentukan ke akun tersebut. Jika akun administrator lokal di VM Anda ada, akun tersebut akan mengatur ulang kata sandi dan jika akun dinonaktifkan, ekstensi VMAccess mengaktifkannya.
Untuk mendapatkan kredensial, gunakan cmdlet Get-Credential.
Untuk informasi selengkapnya, ketik `Get-Help Get-Credential`.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Menentukan nama ekstensi yang ditambahkan cmdlet ini.

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

### -TypeHandlerVersion
Menentukan versi ekstensi yang akan digunakan untuk komputer virtual ini.
Untuk mendapatkan versi, jalankan cmdlet Get-AzVMExtensionImage dengan nilai Microsoft.Compute untuk parameter *PublisherName* dan VMAccessAgent untuk parameter *Jenis* . TypeHandlerVersion harus 2.0 atau lebih tinggi, karena versi 1 tidak digunakan lagi.

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
Cmdlet ini menambahkan VMAccess untuk komputer virtual yang ditentukan parameter ini.

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

### System.Management.Automation.PSCredential

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

## NOTES

## RELATED LINKS

[Get-AzVMAccessExtension](./Get-AzVMAccessExtension.md)

[Remove-AzVMAccessExtension](./Remove-AzVMAccessExtension.md)

[Set-AzVMExtension](./Set-AzVMExtension.md)

[Get-AzVMExtensionImage](./Get-AzVMExtensionImage.md)


