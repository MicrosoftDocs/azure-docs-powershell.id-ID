---
external help file: Microsoft.Azure.PowerShell.Cmdlets.StorageSync.dll-Help.xml
Module Name: Az.StorageSync
online version: https://docs.microsoft.com/powershell/module/az.storagesync/invoke-azstoragesyncchangedetection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/Invoke-AzStorageSyncChangeDetection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/Invoke-AzStorageSyncChangeDetection.md
ms.openlocfilehash: 50880ccbe68e0a1cde9842618c2a9f4050919931
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140183003"
---
# Invoke-AzStorageSyncChangeDetection

## SYNOPSIS
Perintah ini bisa digunakan untuk memulai deteksi perubahan ruang nama secara manual. File dapat ditargetkan ke seluruh file bersama, subfolder, atau kumpulan file. Ketika menjalankan perintah dengan parameter -DirectoryPath atau -Path, maksimum 10.000 item dapat dideteksi. Jika lingkup perubahan diketahui oleh Anda, batasi eksekusi perintah ini ke bagian ruang nama, jadi ubah deteksi bisa selesai dengan cepat dan dalam batas 10.000 item. Alternatifnya, Anda dapat menghindari batas item dengan menjalankan cmdlet tanpa parameter ini, menjalankan deteksi perubahan tingkat berbagi. 

> [!Note]  
> Jika berjalan dengan parameter -DirectoryPath atau -Path, perintah tidak akan mendeteksi perubahan berikut dalam berbagi file Azure:
> - File yang dihapus. 
> - File yang dipindahkan dari berbagi.
> - File yang dihapus dan dibuat dengan nama yang sama.  
> 
>  Jika deteksi perubahan tingkat berbagi diminta, semua perubahan ini akan dideteksi. Perubahan ini juga akan dideteksi saat pekerjaan deteksi [perubahan terjadwal](https://docs.microsoft.com/azure/storage/files/storage-sync-files-troubleshoot?tabs=portal1%2Cazure-portal#afs-change-detection) berjalan.

## SYNTAX

### FullShareStringParameterSet (Default)
```
Invoke-AzStorageSyncChangeDetection [-ResourceGroupName] <String> [-StorageSyncServiceName] <String>
 [-SyncGroupName] <String> -Name <String> [-PassThru] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StringAndDirectoryParameterSet
```
Invoke-AzStorageSyncChangeDetection [-ResourceGroupName] <String> [-StorageSyncServiceName] <String>
 [-SyncGroupName] <String> -Name <String> -DirectoryPath <String> [-Recursive] [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StringAndPathParameterSet
```
Invoke-AzStorageSyncChangeDetection [-ResourceGroupName] <String> [-StorageSyncServiceName] <String>
 [-SyncGroupName] <String> -Name <String> -Path <String[]> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdAndDirectoryParameterSet
```
Invoke-AzStorageSyncChangeDetection [-ResourceId] <String> -DirectoryPath <String> [-Recursive] [-PassThru]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdAndPathParameterSet
```
Invoke-AzStorageSyncChangeDetection [-ResourceId] <String> -Path <String[]> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FullShareResourceIdParameterSet
```
Invoke-AzStorageSyncChangeDetection [-ResourceId] <String> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ObjectAndDirectoryParameterSet
```
Invoke-AzStorageSyncChangeDetection [-InputObject] <PSCloudEndpoint> -DirectoryPath <String> [-Recursive]
 [-PassThru] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ObjectAndPathParameterSet
```
Invoke-AzStorageSyncChangeDetection [-InputObject] <PSCloudEndpoint> -Path <String[]> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FullShareObjectParameterSet
```
Invoke-AzStorageSyncChangeDetection [-InputObject] <PSCloudEndpoint> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Secara berkala, Sinkronisasi File Azure memeriksa ruang nama di dalam sinkronisasi berbagi file Azure untuk perubahan yang masuk ke berbagi file dengan cara lain dari sinkronisasi. Tujuannya adalah untuk mengidentifikasi perubahan ini dan pada akhirnya menyinkronkannya ke server yang tersambung. Perintah ini bisa digunakan untuk memulai deteksi perubahan ruang nama secara manual. File dapat ditargetkan ke seluruh file bersama, subfolder, atau kumpulan file. Jika lingkup perubahan diketahui oleh Anda, batasi eksekusi perintah ini ke bagian ruang nama, sehingga deteksi perubahan item individual bisa selesai dengan cepat dan dalam batas 10.000 item. Jika tidak, jalankan perintah tanpa parameter -DirectoryPath atau -Path untuk menjalankan deteksi perubahan tingkat berbagi penuh.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Invoke-AzStorageSyncChangeDetection -ResourceGroupName "myResourceGroup" -StorageSyncServiceName "myStorageSyncServiceName" -SyncGroupName "mySyncGroupName" -CloudEndpointName "b38fc242-8100-4807-89d0-399cef5863bf" -Path "Data","Reporting\Templates"
```

Dalam contoh ini, deteksi perubahan dijalankan di direktori "Data" dan "Reporting\Templates" dari berbagi file Azure yang disinkronkan. Semua jalur terkait akar dari ruang nama berbagi file Azure.

### Contoh 2
```powershell
PS C:\> Invoke-AzStorageSyncChangeDetection -ResourceGroupName "myResourceGroup" -StorageSyncServiceName "myStorageSyncServiceName" -SyncGroupName "mySyncGroupName" -CloudEndpointName "b38fc242-8100-4807-89d0-399cef5863bf" -Path "Data\results.xslx","Reporting\Templates\generated.pptx"
```

Dalam contoh ini, deteksi perubahan dijalankan untuk kumpulan file yang dikenal sebagai penelepon perintah yang telah berubah. Tujuannya adalah agar sinkronisasi file Azure mendeteksi dan menyinkronkan perubahan ini juga.

### Contoh 3
```powershell
PS C:\> Invoke-AzStorageSyncChangeDetection -ResourceGroupName "myResourceGroup" -StorageSyncServiceName "myStorageSyncServiceName" -SyncGroupName "mySyncGroupName" -CloudEndpointName "b38fc242-8100-4807-89d0-399cef5863bf" -DirectoryPath "Examples" -Recursive
```

Dalam contoh ini, deteksi perubahan dijalankan untuk direktori "Contoh", dan akan mendeteksi perubahan secara berulang dalam subarah. Perlu diingat cmdlet akan gagal jika jalur berisi lebih dari 10.000 item. Jika jalur berisi lebih dari 10.000 item, jalankan perintah pada sub bagian dari ruang nama.

### Contoh 4
```powershell
PS C:\> Invoke-AzStorageSyncChangeDetection -ResourceGroupName "myResourceGroup" -StorageSyncServiceName "myStorageSyncServiceName" -SyncGroupName "mySyncGroupName" -CloudEndpointName "b38fc242-8100-4807-89d0-399cef5863bf"
```

Dalam contoh ini, baik -DirectoryPath maupun -Path tidak diteruskan ke perintah. Ini akan mengaktifkan deteksi perubahan di seluruh berbagi file.

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

### -DirectoryPath
Direktori tempat deteksi perubahan akan dijalankan.

```yaml
Type: System.String
Parameter Sets: StringAndDirectoryParameterSet, ResourceIdAndDirectoryParameterSet, ObjectAndDirectoryParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek CloudEndpoint, biasanya melewati parameter.

```yaml
Type: Microsoft.Azure.Commands.StorageSync.Models.PSCloudEndpoint
Parameter Sets: ObjectAndDirectoryParameterSet, ObjectAndPathParameterSet, FullShareObjectParameterSet
Aliases: CloudEndpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama CloudEndpoint. Nama adalah GUID, bukan nama mudah yang ditampilkan di portal. Untuk mendapatkan CloudEndpointName, gunakan cmdlet Get-AzStorageSyncCloudEndpoint.

```yaml
Type: System.String
Parameter Sets: FullShareStringParameterSet, StringAndDirectoryParameterSet, StringAndPathParameterSet
Aliases: CloudEndpointName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Dalam eksekusi normal, cmdlet ini tidak mengembalikan nilai berhasil. Jika Anda menyediakan parameter PassThru, maka cmdlet akan menulis nilai ke pipeline setelah eksekusi berhasil.

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

### -Path
Jalur tempat deteksi perubahan akan dijalankan.

```yaml
Type: System.String[]
Parameter Sets: StringAndPathParameterSet, ResourceIdAndPathParameterSet, ObjectAndPathParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rekursif
Indikasi apakah deteksi perubahan direktori rekursif.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StringAndDirectoryParameterSet, ResourceIdAndDirectoryParameterSet, ObjectAndDirectoryParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: FullShareStringParameterSet, StringAndDirectoryParameterSet, StringAndPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya CloudEndpoint

```yaml
Type: System.String
Parameter Sets: ResourceIdAndDirectoryParameterSet, ResourceIdAndPathParameterSet, FullShareResourceIdParameterSet
Aliases: CloudEndpointId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageSyncServiceName
Nama StorageSyncService.

```yaml
Type: System.String
Parameter Sets: FullShareStringParameterSet, StringAndDirectoryParameterSet, StringAndPathParameterSet
Aliases: ParentName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SyncGroupName
Nama GrupSinkronisasi.

```yaml
Type: System.String
Parameter Sets: FullShareStringParameterSet, StringAndDirectoryParameterSet, StringAndPathParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.StorageSync.Models.PSServerEndpoint

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS
