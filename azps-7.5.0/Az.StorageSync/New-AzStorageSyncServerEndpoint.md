---
external help file: Microsoft.Azure.PowerShell.Cmdlets.StorageSync.dll-Help.xml
Module Name: Az.StorageSync
online version: https://docs.microsoft.com/powershell/module/Az.storagesync/new-Azstoragesyncserverendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/New-AzStorageSyncServerEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/New-AzStorageSyncServerEndpoint.md
ms.openlocfilehash: 31d17faed45d166f99c8e7cb125a14a684422cbb
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144222842"
---
# New-AzStorageSyncServerEndpoint

## SYNOPSIS
Perintah ini membuat titik akhir server baru pada server terdaftar. Ini memungkinkan jalur yang ditentukan pada server untuk mulai menyinkronkan file dengan titik akhir lain dalam grup sinkronisasi.

## SYNTAX

### StringParameterSet (Default)
```
New-AzStorageSyncServerEndpoint [-ResourceGroupName] <String> [-StorageSyncServiceName] <String>
 [-SyncGroupName] <String> -Name <String> -ServerResourceId <String> -ServerLocalPath <String> [-CloudTiering]
 [-VolumeFreeSpacePercent <Int32>] [-TierFilesOlderThanDays <Int32>] [-InitialDownloadPolicy <String>]
 [-LocalCacheMode <String>] [-InitialUploadPolicy <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ObjectParameterSet
```
New-AzStorageSyncServerEndpoint [-ParentObject] <PSSyncGroup> -Name <String> -ServerResourceId <String>
 -ServerLocalPath <String> [-CloudTiering] [-VolumeFreeSpacePercent <Int32>] [-TierFilesOlderThanDays <Int32>]
 [-InitialDownloadPolicy <String>] [-LocalCacheMode <String>] [-InitialUploadPolicy <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ParentStringParameterSet
```
New-AzStorageSyncServerEndpoint [-ParentResourceId] <String> -Name <String> -ServerResourceId <String>
 -ServerLocalPath <String> [-CloudTiering] [-VolumeFreeSpacePercent <Int32>] [-TierFilesOlderThanDays <Int32>]
 [-InitialDownloadPolicy <String>] [-LocalCacheMode <String>] [-InitialUploadPolicy <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Perintah ini membuat titik akhir server baru pada server terdaftar. Ini memungkinkan jalur yang ditentukan pada server untuk mulai menyinkronkan file dengan titik akhir lain dalam grup sinkronisasi. Jika sudah ada file di titik akhir lain dalam grup sinkronisasi dan lokasi yang baru ditambahkan ini juga berisi file, proses rekonsiliasi akan mencoba menentukan apakah file sebenarnya sama di folder yang sama seperti pada titik akhir lainnya. Namespace akan bergabung dan rekonsiliasi membantu mencegah file konflik. Jika ada file di titik akhir server lain, seringkali lebih baik untuk memulai dengan lokasi kosong di server ini, sehingga file dari cloud turun ke server dalam proses otomatis yang disebut pemulihan bencana cepat. Metadata namespace akan disinkronkan terlebih dahulu, lalu aliran data setiap file diunduh. Jika file diminta oleh pengguna atau aplikasi di luar urutan pengunduhan, file tersebut akan dipanggil kembali dengan prioritas untuk memenuhi permintaan akses. Anda dapat secara opsional menggunakan penjenjangan cloud pada titik akhir server ini untuk menentukan apakah titik akhir ini seharusnya menjadi cache dari kumpulan file lengkap dari cloud. Jika penjenjangan cloud digunakan, unduhan konten file akan berhenti pada titik yang ditentukan oleh kebijakan penjenjangan cloud yang dapat Anda tetapkan.

## EXAMPLES

### Contoh 1
```powershell
$RegisteredServer = Get-AzStorageSyncServer -ResourceGroupName "myResourceGroup" -StorageSyncServiceName "myStorageSyncServiceName"
New-AzStorageSyncServerEndpoint -ResourceGroupName "myResourceGroup" -StorageSyncServiceName "myStorageSyncServiceName" -SyncGroupName "mySyncGroupName" -Name "myServerEndpointName" -ServerResourceId $RegisteredServer.ResourceId -ServerLocalPath "myServerLocalPath" -CloudTiering -TierFilesOlderThanDays "myTierFilesOlderThanDays"
```

Perintah ini membuat titik akhir server baru pada server terdaftar dan menyisipkannya ke dalam grup sinkronisasi. Cara ini merupakan bagian dari topologi titik akhir dan metadata file dan konten lainnya akan segera mulai disinkronkan di antara semua lokasi yang dirujuk sebagai titik akhir dalam grup sinkronisasi.

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

### -CloudTiering
Parameter Penjenjangan Cloud

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

### -InitialDownloadPolicy
Parameter kebijakan pengunduhan awal

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: AvoidTieredFiles, NamespaceOnly, NamespaceThenModifiedFiles

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitialUploadPolicy
Parameter kebijakan unggahan awal

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Merge, ServerAuthoritative

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalCacheMode
Parameter mode cache lokal

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DownloadNewAndModifiedFiles, UpdateLocallyCachedFiles

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama ServerEndpoint.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServerEndpointName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentObject
Objek SyncGroup, biasanya melewati parameter .

```yaml
Type: Microsoft.Azure.Commands.StorageSync.Models.PSSyncGroup
Parameter Sets: ObjectParameterSet
Aliases: SyncGroup

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ParentResourceId
Id Sumber Daya Induk SyncGroup

```yaml
Type: System.String
Parameter Sets: ParentStringParameterSet
Aliases: SyncGroupId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: StringParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerLocalPath
Parameter Jalur Lokal Server

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

### -ServerResourceId
Id Sumber Daya RegisteredServer

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

### -StorageSyncServiceName
Nama StorageSyncService.

```yaml
Type: System.String
Parameter Sets: StringParameterSet
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
Parameter Sets: StringParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TierFilesOlderThanDays
File Tingkat Lebih Lama dari Hari Parameter

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VolumeFreeSpacePercent
Parameter Persen Ruang Bebas Volume

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.StorageSync.Models.PSSyncGroup

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.StorageSync.Models.PSServerEndpoint

## NOTES

## RELATED LINKS
