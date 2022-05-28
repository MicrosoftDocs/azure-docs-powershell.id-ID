---
external help file: Microsoft.Azure.PowerShell.Cmdlets.StorageSync.dll-Help.xml
Module Name: Az.StorageSync
online version: https://docs.microsoft.com/powershell/module/az.storagesync/invoke-azstoragesyncchangedetection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/Invoke-AzStorageSyncChangeDetection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/Invoke-AzStorageSyncChangeDetection.md
ms.openlocfilehash: 71e41aa13e13d178a98fa6cc3e8c9101b1dd069b
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145500048"
---
# Invoke-AzStorageSyncChangeDetection

## SYNOPSIS
Perintah ini dapat digunakan untuk memulai deteksi perubahan namespace secara manual. Ini dapat ditargetkan ke seluruh berbagi, subfolder, atau set file. Saat menjalankan perintah dengan parameter -DirectoryPath atau -Path, maksimal 10.000 item dapat dideteksi. Jika cakupan perubahan diketahui oleh Anda, batasi eksekusi perintah ini ke bagian namespace layanan, sehingga deteksi perubahan dapat selesai dengan cepat dan dalam batas 10.000 item. Atau, Anda dapat menghindari batas item dengan menjalankan cmdlet tanpa parameter ini, memanggil deteksi perubahan tingkat berbagi. 

> [!Note]  
> Jika dijalankan dengan parameter -DirectoryPath atau -Path, perintah tidak akan mendeteksi perubahan berikut dalam berbagi file Azure:
> - File yang dihapus. 
> - File yang dipindahkan dari berbagi.
> - File yang dihapus dan dibuat dengan nama yang sama.  
> 
>  Jika deteksi perubahan tingkat berbagi dipanggil, semua perubahan ini akan terdeteksi. Perubahan ini juga akan terdeteksi ketika [pekerjaan deteksi perubahan](https://docs.microsoft.com/azure/storage/files/storage-sync-files-troubleshoot?tabs=portal1%2Cazure-portal#afs-change-detection) terjadwal berjalan.

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
Secara berkala, Azure File Sync memeriksa namespace di dalam berbagi file Azure yang disinkronkan untuk perubahan yang masuk ke berbagi file dengan cara lain selain sinkronisasi. Tujuannya adalah untuk mengidentifikasi perubahan ini dan pada akhirnya menyinkronkannya ke server yang terhubung. Perintah ini dapat digunakan untuk memulai deteksi perubahan namespace secara manual. Ini dapat ditargetkan ke seluruh berbagi, subfolder, atau set file. Jika cakupan perubahan diketahui oleh Anda, batasi eksekusi perintah ini ke bagian namespace layanan, sehingga deteksi perubahan item individual dapat selesai dengan cepat dan dalam batas 10.000 item. Jika tidak, jalankan perintah tanpa parameter -DirectoryPath atau -Path untuk memanggil deteksi perubahan tingkat berbagi penuh.

## EXAMPLES

### Contoh 1
```powershell
Invoke-AzStorageSyncChangeDetection -ResourceGroupName "myResourceGroup" -StorageSyncServiceName "myStorageSyncServiceName" -SyncGroupName "mySyncGroupName" -CloudEndpointName "b38fc242-8100-4807-89d0-399cef5863bf" -Path "Data","Reporting\Templates"
```

Dalam contoh ini, deteksi perubahan dijalankan di direktori "Data" dan "Reporting\Templates" dari berbagi file Azure yang disinkronkan. Semua jalur relatif terhadap akar namespace berbagi file Azure.

### Contoh 2
```powershell
Invoke-AzStorageSyncChangeDetection -ResourceGroupName "myResourceGroup" -StorageSyncServiceName "myStorageSyncServiceName" -SyncGroupName "mySyncGroupName" -CloudEndpointName "b38fc242-8100-4807-89d0-399cef5863bf" -Path "Data\results.xslx","Reporting\Templates\generated.pptx"
```

Dalam contoh ini, deteksi perubahan dijalankan untuk sekumpulan file yang diketahui oleh pemanggil perintah yang telah berubah. Tujuannya adalah agar sinkronisasi file Azure mendeteksi dan menyinkronkan perubahan ini juga.

### Contoh: 3
```powershell
Invoke-AzStorageSyncChangeDetection -ResourceGroupName "myResourceGroup" -StorageSyncServiceName "myStorageSyncServiceName" -SyncGroupName "mySyncGroupName" -CloudEndpointName "b38fc242-8100-4807-89d0-399cef5863bf" -DirectoryPath "Examples" -Recursive
```

Dalam contoh ini, deteksi perubahan dijalankan untuk direktori "Contoh" dan akan secara rekursif mendeteksi perubahan dalam subdirektori. Perlu diingat cmdlet akan gagal jika jalur berisi lebih dari 10.000 item. Jika jalur berisi lebih dari 10.000 item, jalankan perintah pada sub-bagian namespace.

### Contoh 4
```powershell
Invoke-AzStorageSyncChangeDetection -ResourceGroupName "myResourceGroup" -StorageSyncServiceName "myStorageSyncServiceName" -SyncGroupName "mySyncGroupName" -CloudEndpointName "b38fc242-8100-4807-89d0-399cef5863bf"
```

Dalam contoh ini, baik -DirectoryPath maupun -Path tidak diteruskan ke perintah. Ini akan memanggil deteksi perubahan pada seluruh berbagi file.

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
Direktori tempat deteksi perubahan akan dilakukan.

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
Objek CloudEndpoint, biasanya melewati parameter .

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

### -Name
Nama CloudEndpoint. Nama tersebut adalah GUID, bukan nama yang mudah diingat yang ditampilkan di portal. Untuk mendapatkan CloudEndpointName, gunakan cmdlet Get-AzStorageSyncCloudEndpoint.

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
Dalam eksekusi normal, cmdlet ini tidak mengembalikan nilai pada keberhasilan. Jika Anda memberikan parameter PassThru, maka cmdlet akan menulis nilai ke alur setelah eksekusi berhasil.

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

### -Jalur
Jalur tempat deteksi perubahan akan dilakukan.

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
Nama SyncGroup.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.StorageSync.Models.PSServerEndpoint

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS
