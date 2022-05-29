---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/set-azstorageblobimmutabilitypolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageBlobImmutabilityPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageBlobImmutabilityPolicy.md
ms.openlocfilehash: de7d9a9345ec0c77cbe9cc3d8f3b89fe0908be03
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145714258"
---
# Set-AzStorageBlobImmutabilityPolicy

## SYNOPSIS
Membuat atau memperbarui ImmutabilityPolicy dari blob Storage.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.storage/set-azstorageblobimmutabilitypolicy) untuk informasi terbaru.

## SYNTAX

### NamePipeline (Default)
```
Set-AzStorageBlobImmutabilityPolicy [-Blob] <String> [-Container] <String> -ExpiresOn <DateTimeOffset>
 [-PolicyMode <String>] [-TagCondition <String>] [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### BlobPipeline
```
Set-AzStorageBlobImmutabilityPolicy -BlobBaseClient <BlobBaseClient> -ExpiresOn <DateTimeOffset>
 [-PolicyMode <String>] [-TagCondition <String>] [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzStorageBlobImmutabilityPolicy** membuat atau memperbarui ImmutabilityPolicy dari blob Storage. Cmdlet hanya berfungsi ketika kontainer blob telah mengaktifkan Storage yang tidak dapat diubah dengan penerapan versi.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui kebijakan kekekalan blob Storage.
```
PS C:\> $blob = Set-AzStorageBlobImmutabilityPolicy -Container $containerName -Blob $blobname  -ExpiresOn (Get-Date).AddDays(100) -PolicyMode Unlocked

PS C:\> $blob

   AccountName: mystorageaccount, ContainerName: mycontainer

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
testblob             BlockBlob 10485760        application/octet-stream       2021-07-19 08:56:00Z Hot                                     False      2021-07-19T08:56:01.8120788Z *   

PS C:\> $blob.BlobProperties.ImmutabilityPolicy

ExpiresOn                    PolicyMode
---------                    ----------
10/27/2021 8:56:32 AM +00:00   Unlocked
```

Perintah ini membuat atau memperbarui ImmutabilityPolicy dari blob Storage, lalu menampilkan blob dan ImmutabilityPolicy-nya.
Perintah hanya berfungsi ketika kontainer blob telah mengaktifkan Storage yang tidak dapat diubah dengan penerapan versi.

## PARAMETERS

### -Blob
Nama blob

```yaml
Type: System.String
Parameter Sets: NamePipeline
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
Parameter Sets: BlobPipeline
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
Parameter Sets: NamePipeline
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

### -ExpiresOn
Blob ImmutabilityPolicy ExpiresOn

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyMode
Blob ImmutabilityPolicy PolicyMode

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Unlocked, Locked, Mutable

Required: False
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
Pernyataan ekspresi Tag opsional untuk memeriksa kondisi kecocokan. Permintaan blob akan gagal ketika tag blob tidak cocok dengan ekspresi yang diberikan. Lihat detail di https://docs.microsoft.com/en-us/rest/api/storageservices/specifying-conditional-headers-for-blob-service-operations#tags-conditional-operations.

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
