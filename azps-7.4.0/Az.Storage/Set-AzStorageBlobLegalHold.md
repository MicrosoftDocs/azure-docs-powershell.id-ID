---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/set-azstoragebloblegalhold
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageBlobLegalHold.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageBlobLegalHold.md
ms.openlocfilehash: e6b7980af5cdab62c102e10a907dbfa9e3cac7ec
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144690326"
---
# Set-AzStorageBlobLegalHold

## SYNOPSIS
Mengaktifkan atau menonaktifkan penahanan legal pada blob Storage.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.storage/set-azstoragebloblegalhold) untuk informasi terbaru.

## SYNTAX

### NamePipelineEnable (Default)
```
Set-AzStorageBlobLegalHold [-Blob] <String> [-Container] <String> [-EnableLegalHold] [-TagCondition <String>]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### BlobPipelineEnable
```
Set-AzStorageBlobLegalHold -BlobBaseClient <BlobBaseClient> [-EnableLegalHold] [-TagCondition <String>]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### BlobPipelineDisable
```
Set-AzStorageBlobLegalHold -BlobBaseClient <BlobBaseClient> [-DisableLegalHold] [-TagCondition <String>]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### NamePipelineDisable
```
Set-AzStorageBlobLegalHold [-Blob] <String> [-Container] <String> [-DisableLegalHold] [-TagCondition <String>]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Set-AzStorageBlobLegalHold** memungkinkan atau menonaktifkan penahanan legal pada blob Storage.
Cmdlet hanya berfungsi ketika kontainer blob telah mengaktifkan Storage yang tidak dapat diubah dengan penerapan versi.

## EXAMPLES

### Contoh 1: Aktifkan penahanan legal pada blob Storage.
```
PS C:\> $blob = Set-AzStorageBlobLegalHold -Container $containerName -Blob $blobname  -EnableLegalHold

PS C:\> $blob

   AccountName: mystorageaccount, ContainerName: mycontainer

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
testblob             BlockBlob 10485760        application/octet-stream       2021-07-19 08:56:00Z Hot                                     False      2021-07-19T08:56:01.8120788Z *

PS C:\> $blob.BlobProperties.HasLegalHold
True
```

Perintah ini memungkinkan penahanan legal pada blob Storage, lalu menampilkan hasilnya.
Perintah hanya berfungsi ketika kontainer blob telah mengaktifkan Storage yang tidak dapat diubah dengan penerapan versi.

### Contoh 2: Nonaktifkan penahanan legal pada blob Storage dengan alur.
```
PS C:\> $blob = Get-AzStorageBlob -Container $containerName -Blob $blobname | Set-AzStorageBlobLegalHold -DisableLegalHold

PS C:\> $blob

   AccountName: mystorageaccount, ContainerName: mycontainer

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
testblob             BlockBlob 10485760        application/octet-stream       2021-07-19 08:56:00Z Hot                                     False      2021-07-19T08:56:01.8120788Z *

PS C:\> $blob.BlobProperties.HasLegalHold
False
```

Perintah ini menonaktifkan penahanan legal pada blob Storage dengan alur, lalu menampilkan hasilnya.
Perintah hanya berfungsi ketika kontainer blob telah mengaktifkan Storage yang tidak dapat diubah dengan penerapan versi.

## PARAMETERS

### -Blob
Nama blob

```yaml
Type: System.String
Parameter Sets: NamePipelineEnable, NamePipelineDisable
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BlobBaseClient
Objek BlobBaseClient

```yaml
Type: Azure.Storage.Blobs.Specialized.BlobBaseClient
Parameter Sets: BlobPipelineEnable, BlobPipelineDisable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientTimeoutPerRequest
Waktu eksekusi maksimum sisi klien untuk setiap permintaan dalam detik.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: ClientTimeoutPerRequestInSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConcurrentTaskCount
Jumlah total tugas asinkron bersamaan.
Nilai defaultnya adalah 10.

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

### -Kontainer
Nama kontainer

```yaml
Type: System.String
Parameter Sets: NamePipelineEnable, NamePipelineDisable
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Context
Objek Konteks Azure Storage

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableLegalHold
Nonaktifkan LegalHold pada Blob.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: BlobPipelineDisable, NamePipelineDisable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableLegalHold
Aktifkan LegalHold pada Blob.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NamePipelineEnable, BlobPipelineEnable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Waktu server habis untuk setiap permintaan dalam hitung detik.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: ServerTimeoutPerRequestInSeconds

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TagCondition
Pernyataan ekspresi Tag opsional untuk memeriksa kondisi kecocokan. Permintaan blob akan gagal ketika tag blob tidak cocok dengan ekspresi yang diberikan. Lihat detailnya di https://docs.microsoft.com/en-us/rest/api/storageservices/specifying-conditional-headers-for-blob-service-operations#tags-conditional-operations.

```yaml
Type: System.String
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

### Azure. Storage. Blobs.Specialized.BlobBaseClient

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageBlob

## NOTES

## RELATED LINKS
