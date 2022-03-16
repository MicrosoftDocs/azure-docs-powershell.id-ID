---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: FB9ACBA2-081E-4876-A21A-F5BA11CBEDA2
online version: https://docs.microsoft.com/powershell/module/az.compute/publish-azvmdscconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Publish-AzVMDscConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Publish-AzVMDscConfiguration.md
ms.openlocfilehash: 996b1696fe2709dd94c1142d37f55e808d8a6c60
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140092367"
---
# Publish-AzVMDscConfiguration

## SYNOPSIS
Mengunggah skrip DSC ke penyimpanan blob Azure.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.compute/publish-azvmdscconfiguration) untuk informasi terkini.

## SYNTAX

### UploadArchive (Default)
```
Publish-AzVMDscConfiguration [-ResourceGroupName] <String> [-ConfigurationPath] <String>
 [[-ContainerName] <String>] [-StorageAccountName] <String> [-StorageEndpointSuffix <String>] [-Force]
 [-SkipDependencyDetection] [-ConfigurationDataPath <String>] [-AdditionalPath <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CreateArchive
```
Publish-AzVMDscConfiguration [-ConfigurationPath] <String> [[-OutputArchivePath] <String>] [-Force]
 [-SkipDependencyDetection] [-ConfigurationDataPath <String>] [-AdditionalPath <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Publish-AzVMDscConfiguration** mengunggah skrip Konfigurasi Status Yang Diinginkan (DSC, Desired State Configuration) ke penyimpanan blob Azure, yang nantinya dapat diterapkan ke komputer virtual Azure menggunakan cmdlet Set-AzVMDscExtension cmdlet.

## EXAMPLES

### Contoh 1: Membuat .zip ingin mengunggahnya ke penyimpanan Azure
```
PS C:\> Publish-AzVMDscConfiguration ".\MyConfiguration.ps1"
```

Perintah ini membuat paket .zip untuk skrip tertentu dan modul sumber daya yang tergantung dan mengunggahnya ke penyimpanan Azure.

### Contoh 2: Buat .zip kemudian simpan ke file lokal
```
PS C:\> Publish-AzVMDscConfiguration ".\MyConfiguration.ps1" -OutputArchivePath ".\MyConfiguration.ps1.zip"
```

Perintah ini membuat paket .zip untuk skrip tertentu dan modul sumber daya dependen dan menyimpannya dalam file lokal yang bernama .\MyConfiguration.ps1.zip.

### Contoh 3: Tambahkan konfigurasi ke arsip lalu unggah ke penyimpanan
```
PS C:\> Publish-AzVMDscConfiguration -ConfigurationPath "C:\Sample.ps1" -SkipDependencyDetection
```

Perintah ini menambahkan konfigurasi yang Sample.ps1 arsip konfigurasi untuk diunggah ke penyimpanan Azure dan melewatkan modul sumber daya dependen.

### Contoh 4: Tambahkan data konfigurasi dan konfigurasi ke arsip lalu unggah data ke penyimpanan
```
PS C:\> Publish-AzVMDscConfiguration -ConfigurationPath "C:\Sample.ps1" -ConfigurationDataPath "C:\SampleData.psd1"
```

Perintah ini menambahkan konfigurasi yang Sample.ps1 data konfigurasi bernama SampleData.psd1 ke arsip konfigurasi untuk diunggah ke penyimpanan Azure.

### Contoh 5: Tambahkan konfigurasi, data konfigurasi, dan konten tambahan ke arsip lalu unggah ke penyimpanan
```
PS C:\> Publish-AzVMDscConfiguration -ConfigurationPath "C:\Sample.ps1" -AdditionalPath @("C:\ContentDir1", "C:\File.txt") -ConfigurationDataPath "C:\SampleData.psd1"
```

Perintah ini menambahkan konfigurasi bernama Sample.ps1, data konfigurasi SampleData.psd1, dan konten tambahan ke arsip konfigurasi untuk diunggah ke penyimpanan Azure.

## PARAMETERS

### -AdditionalPath
Menentukan jalur file atau direktori yang akan disertakan dalam arsip konfigurasi.
File akan diunduh ke mesin virtual bersama dengan konfigurasi.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationDataPath
Menentukan jalur file .psd1 yang menentukan data untuk konfigurasi.
Ini akan ditambahkan ke arsip konfigurasi lalu diteruskan ke fungsi konfigurasi.
Jalur ini ditimpa oleh jalur data konfigurasi yang disediakan melalui cmdlet Set-AzVMDscExtension

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

### -ConfigurationPath
Menentukan jalur file yang berisi satu atau beberapa konfigurasi.
File dapat merupakan file Windows PowerShell skrip (.ps1) atau file modul Windows PowerShell (.psm1).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ContainerName
Menentukan nama wadah penyimpanan Azure tempat konfigurasi diunggah.

```yaml
Type: System.String
Parameter Sets: UploadArchive
Aliases:

Required: False
Position: 4
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

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

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

### -OutputArchivePath
Menentukan jalur file lokal .zip untuk menulis arsip konfigurasi.
Ketika parameter ini digunakan, skrip konfigurasi tidak diunggah ke penyimpanan blob Azure.

```yaml
Type: System.String
Parameter Sets: CreateArchive
Aliases: ConfigurationArchivePath

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi akun penyimpanan.

```yaml
Type: System.String
Parameter Sets: UploadArchive
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipDependencyDetection
Mengindikasikan bahwa cmdlet ini mengecualikan dependensi sumber daya DSC dari arsip konfigurasi.

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

### -StorageAccountName
Menentukan nama akun penyimpanan Azure yang digunakan untuk mengunggah skrip konfigurasi ke wadah yang ditentukan oleh parameter *ContainerName* .

```yaml
Type: System.String
Parameter Sets: UploadArchive
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageEndpointFix
Menentukan akhiran untuk titik akhir penyimpanan.

```yaml
Type: System.String
Parameter Sets: UploadArchive
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

## OUTPUTS

### System.String

## CATATAN

## RELATED LINKS

[Get-AzVMDscExtension](./Get-AzVMDscExtension.md)

[Remove-AzVMDscExtension](./Remove-AzVMDscExtension.md)

[Set-AzVMDscExtension](./Set-AzVMDscExtension.md)


