---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
ms.assetid: FB9ACBA2-081E-4876-A21A-F5BA11CBEDA2
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Publish-AzureRmVMDscConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Stack/Commands.Compute/help/Publish-AzureRmVMDscConfiguration.md
ms.openlocfilehash: ed65956b777ca760be3034f656c25d6c86e5aa3c
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428550"
---
# Publish-AzureRmVMDscConfiguration

## SYNOPSIS
Mengunggah skrip DSC ke penyimpanan blob Azure.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### UploadArchive (Default)
```
Publish-AzureRmVMDscConfiguration [-ResourceGroupName] <String> [-ConfigurationPath] <String>
 [[-ContainerName] <String>] [-StorageAccountName] <String> [-StorageEndpointSuffix <String>] [-Force]
 [-SkipDependencyDetection] [-ConfigurationDataPath <String>] [-AdditionalPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CreateArchive
```
Publish-AzureRmVMDscConfiguration [-ConfigurationPath] <String> [[-OutputArchivePath] <String>] [-Force]
 [-SkipDependencyDetection] [-ConfigurationDataPath <String>] [-AdditionalPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Publish-AzureRmVMDscConfiguration** mengunggah skrip Konfigurasi Status Yang Diinginkan (DSC) ke penyimpanan blob Azure, yang nantinya dapat diterapkan ke komputer virtual Azure menggunakan cmdlet Set-AzureRmVMDscExtension.

## EXAMPLES

### Contoh 1: Membuat .zip dan mengunggahnya ke penyimpanan Azure
```
PS C:\> Publish-AzureRmVMDscConfiguration ".\MyConfiguration.ps1"
```

Perintah ini akan membuat .zip tambahan untuk skrip tertentu dan modul sumber daya yang tergantung, lalu mengunggahnya ke penyimpanan Azure.

### Contoh 2: Buat .zip kemudian simpan ke file lokal
```
PS C:\> Publish-AzureRmVMDscConfiguration ".\MyConfiguration.ps1" -OutputArchivePath ".\MyConfiguration.ps1.zip"
```

Perintah ini membuat paket .zip untuk skrip tertentu dan modul sumber daya dependen dan menyimpannya dalam file lokal yang bernama .\MyConfiguration.ps1.zip.

### Contoh 3: Tambahkan konfigurasi ke arsip lalu unggah ke penyimpanan
```
PS C:\> Publish-AzureRmVMDscConfiguration -ConfigurationPath "C:\Sample.ps1" -SkipDependencyDetection
```

Perintah ini menambahkan konfigurasi yang Sample.ps1 ke arsip konfigurasi untuk diunggah ke penyimpanan Azure dan melewatkan modul sumber daya dependen.

### Contoh 4: Tambahkan data konfigurasi dan konfigurasi ke arsip lalu unggah data ke penyimpanan
```
PS C:\> Publish-AzureRmVMDscConfiguration -ConfigurationPath "C:\Sample.ps1" -ConfigurationDataPath "C:\SampleData.psd1"
```

Perintah ini menambahkan konfigurasi yang Sample.ps1 data konfigurasi bernama SampleData.psd1 ke arsip konfigurasi untuk diunggah ke penyimpanan Azure.

### Contoh 5: Tambahkan konfigurasi, data konfigurasi, dan konten tambahan ke arsip lalu unggah ke penyimpanan
```
PS C:\> Publish-AzureRmVMDscConfiguration -ConfigurationPath "C:\Sample.ps1" -AdditionalPath @("C:\ContentDir1", "C:\File.txt") -ConfigurationDataPath "C:\SampleData.psd1"
```

Perintah ini menambahkan konfigurasi bernama Sample.ps1, data konfigurasi SampleData.psd1, dan konten tambahan ke arsip konfigurasi untuk diunggah ke penyimpanan Azure.

## PARAMETERS

### -AdditionalPath
Menentukan jalur file atau direktori yang akan disertakan dalam arsip konfigurasi.
File akan diunduh ke mesin virtual bersama dengan konfigurasi.

```yaml
Type: String[]
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
Jalur ini ditimpa oleh jalur data konfigurasi yang disediakan melalui cmdlet Set-AzureRmVMDscExtension

```yaml
Type: String
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
File dapat merupakan file Windows PowerShell script (.ps1) atau file modul Windows PowerShell (.psm1).

```yaml
Type: String
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
Type: String
Parameter Sets: UploadArchive
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

```yaml
Type: SwitchParameter
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
Type: String
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
Type: String
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountName
Menentukan nama akun penyimpanan Azure yang digunakan untuk mengunggah skrip konfigurasi ke wadah yang ditentukan oleh parameter *ContainerName.*

```yaml
Type: String
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
Type: String
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
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRmVMDscExtension](./Get-AzureRmVMDscExtension.md)

[Remove-AzureRmVMDscExtension](./Remove-AzureRmVMDscExtension.md)

[Set-AzureRmVMDscExtension](./Set-AzureRmVMDscExtension.md)


