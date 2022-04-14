---
external help file: Microsoft.Azure.PowerShell.Cmdlets.MachineLearning.dll-Help.xml
Module Name: Az.MachineLearning
online version: https://docs.microsoft.com/powershell/module/az.machinelearning/update-azmlwebservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearning/MachineLearning/help/Update-AzMlWebService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearning/MachineLearning/help/Update-AzMlWebService.md
ms.openlocfilehash: 311dadeb73e893cae4448efbe04647de0e097a51
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141865796"
---
# Update-AzMlWebService

## SYNOPSIS
Memperbarui properti sumber daya layanan web yang sudah ada.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.machinelearning/update-azmlwebservice) untuk informasi terbaru.

## SYNTAX

### PembaruanFromParameters
```
Update-AzMlWebService -ResourceGroupName <String> -Name <String> [-Title <String>] [-Description <String>]
 [-IsReadOnly] [-Keys <WebServiceKeys>] [-StorageAccountKey <String>] [-Diagnostics <DiagnosticsConfiguration>]
 [-RealtimeConfiguration <RealtimeConfiguration>] [-Assets <Hashtable>]
 [-Input <ServiceInputOutputSpecification>] [-Output <ServiceInputOutputSpecification>]
 [-Parameters <Hashtable>] [-Package <GraphPackage>] [-Force] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### PembaruanFromObject
```
Update-AzMlWebService -ResourceGroupName <String> -Name <String> -ServiceUpdates <WebService> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Update-AzMlWebService memungkinkan Anda memperbarui properti non-statis layanan web.
Cmdlet bekerja sebagai operasi patch.
Hanya lewati properti yang ingin Anda ubah.

## EXAMPLES

### Contoh 1: Argumen pembaruan selektif
```
Update-AzMlWebService -ResourceGroupName "myresourcegroup" -Name "mywebservicename" -Description "new update to description" -Keys @{Primary='changed primary key'} -Diagnostics @{Level='All'}
```

Di sini, kami mengubah deskripsi, kunci akses utama, dan mengaktifkan kumpulan diagnostik untuk semua jejak selama runtime untuk layanan web.

### Contoh 2: Pembaruan berdasarkan instans layanan web
```
$updates = @{ Properties = @{ Title="New Title"; RealtimeConfiguration = @{ MaxConcurrentCalls=25 }}}

Update-AzMlWebService -ResourceGroupName "myresourcegroup" -Name "mywebservicename" -ServiceUpdates $updates
```

Contoh pertama membuat definisi layanan web, yang hanya berisi bidang yang akan diperbarui, lalu memanggil Update-AzMlWebService untuk menerapkannya menggunakan parameter ServiceUpdates.

## PARAMETERS

### -Aset
Kumpulan aset (misalnya modul, kumpulan data) yang menyusun layanan web.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: UpdateFromParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Deskripsi
Nilai baru untuk deskripsi layanan web.
Hal ini terlihat dalam skema Swagger API layanan.

```yaml
Type: System.String
Parameter Sets: UpdateFromParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Diagnostik
Pengaturan yang mengontrol kumpulan jejak diagnostik untuk layanan web.

```yaml
Type: Microsoft.Azure.Management.MachineLearning.WebServices.Models.DiagnosticsConfiguration
Parameter Sets: UpdateFromParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Paksa
Jangan meminta konfirmasi.

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

### -Input
Definisi untuk input layanan web, disediakan sebagai konstruksi skema Swagger.

```yaml
Type: Microsoft.Azure.Management.MachineLearning.WebServices.Models.ServiceInputOutputSpecification
Parameter Sets: UpdateFromParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsReadOnly
Menentukan bahwa layanan web ini sudah dibaca.
Setelah diatur, layanan web dapat diperbarui lebih lama, termasuk mengubah nilai properti ini, dan hanya dapat dihapus.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UpdateFromParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Keys
Memperbarui satu atau kedua kunci akses yang digunakan untuk mengautentikasi panggilan ke API runtime layanan.

```yaml
Type: Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebServiceKeys
Parameter Sets: UpdateFromParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sumber daya layanan web yang akan diperbarui.

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

### -Output
Definisi untuk output layanan web, disediakan sebagai konstruksi skema Swagger.

```yaml
Type: Microsoft.Azure.Management.MachineLearning.WebServices.Models.ServiceInputOutputSpecification
Parameter Sets: UpdateFromParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Paket
Definisi paket grafik yang menentukan layanan web ini.

```yaml
Type: Microsoft.Azure.Management.MachineLearning.WebServices.Models.GraphPackage
Parameter Sets: UpdateFromParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameters
Kumpulan nilai parameter global yang ditentukan untuk layanan web, yang diberikan sebagai nama parameter global -\> kumpulan nilai default.
Jika tidak ada nilai default yang ditentukan, parameter dianggap diperlukan.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: UpdateFromParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RealtimeConfiguration
Pembaruan untuk konfigurasi titik akhir realtime layanan.

```yaml
Type: Microsoft.Azure.Management.MachineLearning.WebServices.Models.RealtimeConfiguration
Parameter Sets: UpdateFromParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya yang berisi layanan web yang akan diperbarui.

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

### -ServiceUpdates
Sekumpulan pembaruan untuk diterapkan ke layanan web yang disediakan sebagai contoh definisi layanan web.
Hanya bidang non-statis yang dimodifikasi.

```yaml
Type: Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService
Parameter Sets: UpdateFromObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageAccountKey
Memutar kunci akses untuk akun penyimpanan yang terkait dengan layanan web.

```yaml
Type: System.String
Parameter Sets: UpdateFromParameters
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Judul
Nilai baru untuk judul layanan web.
Hal ini terlihat dalam skema Swagger API layanan.

```yaml
Type: System.String
Parameter Sets: UpdateFromParameters
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService

## OUTPUTS

### Microsoft.Azure.Management.MachineLearning.WebServices.Models.WebService

## CATATAN
Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, mesin, pembelajaran mesin, azureml

## RELATED LINKS
