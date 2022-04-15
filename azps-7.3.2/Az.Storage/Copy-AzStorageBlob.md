---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/copy-azstorageblob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Copy-AzStorageBlob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Copy-AzStorageBlob.md
ms.openlocfilehash: 2f141e1eee39720de3a5220a6f4a6deb959822d1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142398599"
---
# Copy-AzStorageBlob

## SYNOPSIS
Salin gumpalan secara sinkron.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.storage/copy-azstorageblob) untuk informasi terbaru.

## SYNTAX

### ContainerName (Default)
```
Copy-AzStorageBlob [-SrcBlob] <String> -SrcContainer <String> -DestContainer <String> [-DestBlob <String>]
 [-StandardBlobTier <String>] [-RehydratePriority <RehydratePriority>] [-EncryptionScope <String>]
 [-Context <IStorageContext>] [-DestContext <IStorageContext>] [-Force] [-AsJob] [-TagCondition <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BlobInstance
```
Copy-AzStorageBlob [-BlobBaseClient <BlobBaseClient>] -DestContainer <String> [-DestBlob <String>]
 [-StandardBlobTier <String>] [-RehydratePriority <RehydratePriority>] [-EncryptionScope <String>]
 [-Context <IStorageContext>] [-DestContext <IStorageContext>] [-Force] [-AsJob] [-TagCondition <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UriPipeline
```
Copy-AzStorageBlob -AbsoluteUri <String> -DestContainer <String> -DestBlob <String>
 [-StandardBlobTier <String>] [-RehydratePriority <RehydratePriority>] [-EncryptionScope <String>]
 [-Context <IStorageContext>] [-DestContext <IStorageContext>] [-Force] [-AsJob] [-TagCondition <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Copy-AzStorageBlob** menyalin blob secara sinkron, saat ini hanya mendukung blok blob.

## EXAMPLES

### Contoh 1: Menyalin blob bernama ke blob lain
```
C:\PS> $destBlob = Copy-AzStorageBlob -SrcContainer "sourcecontainername" -SrcBlob "srcblobname" -DestContainer "destcontainername" -DestBlob "destblobname"
```

Perintah ini menyalin blob dari wadah sumber ke wadah tujuan dengan nama blob baru. 

### Contoh 2: Salin blob dari objek blob
```
C:\PS> $srcBlob = Get-AzStorageBlob -Container $containerName -Blob $blobName  -Context $ctx 
C:\PS> $destBlob =  $srcBlob | Copy-AzStorageBlob  -DestContainer "destcontainername" -DestBlob "destblobname"
```

Perintah ini menyalin blob dari objek blob sumber ke wadah tujuan dengan nama blob baru.

### Contoh 3: Copy blob from a blob Uri
```
C:\PS> $srcBlobUri = New-AzStorageBlobSASToken -Container $srcContainerName -Blob $srcBlobName -Permission rt -ExpiryTime (Get-Date).AddDays(7) -FullUri 
C:\PS> $destBlob = Copy-AzStorageBlob -AbsoluteUri $srcBlobUri -DestContainer "destcontainername" -DestBlob "destblobname"
```

Perintah pertama membuat Uri gumpalan dari blob sumber, dengan sas token izin "rt". Perintah kedua menyalin dari Uri blob sumber ke blob tujuan.

### Contoh 4: Memperbarui lingkup enkripsi blok blob
```
C:\PS> $blob = Copy-AzStorageBlob -SrcContainer $containerName -SrcBlob $blobname -DestContainer $containername -EncryptionScope $newScopeName -Force
```

Perintah ini memperbarui lingkup enkripsi blok blob dengan menyalinnya sendiri dengan lingkup enkripsi baru.

## PARAMETERS

### -AbsoluteUri
Sumber blob uri

```yaml
Type: System.String
Parameter Sets: UriPipeline
Aliases: SrcUri, SourceUri

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -BlobBaseClient
Objek BlobBaseClient

```yaml
Type: Azure.Storage.Blobs.Specialized.BlobBaseClient
Parameter Sets: BlobInstance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konteks
Objek Konteks Azure Storage Sumber

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: ContainerName, BlobInstance
Aliases: SrcContext, SourceContext

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: UriPipeline
Aliases: SrcContext, SourceContext

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

### -DestBlob
Nama blob tujuan

```yaml
Type: System.String
Parameter Sets: ContainerName, BlobInstance
Aliases: DestinationBlob

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: UriPipeline
Aliases: DestinationBlob

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestContainer
Nama wadah tujuan

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DestinationContainer

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestContext
Objek konteks Storage tujuan

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext
Parameter Sets: (All)
Aliases: DestinationContext

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionScope
Lingkup enkripsi yang akan digunakan saat membuat permintaan ke lingkup dest.

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

### -Paksa
Memaksa untuk menimpa blob atau file yang sudah ada

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

### -RehydratePriority
Blokir Blob RehydratePriority.
Menunjukkan prioritas untuk merehidrasi blob yang diarsipkan.
Nilai yang valid adalah Tinggi/Standar.

```yaml
Type: Microsoft.Azure.Storage.Blob.RehydratePriority
Parameter Sets: (All)
Aliases:
Accepted values: Standard, High

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcBlob
Nama blob

```yaml
Type: System.String
Parameter Sets: ContainerName
Aliases: SourceBlob

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SrcContainer
Nama Wadah Sumber

```yaml
Type: System.String
Parameter Sets: ContainerName
Aliases: SourceContainer

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StandardBlobTier
Block Blob Tier, nilai yang valid adalah Hot/Cool/Archive.
Lihat detailnya di https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blob-storage-tiers

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Hot, Cool, Archive

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TagCondition
Pernyataan ekspresi Tag Opsional untuk memeriksa kondisi kecocokan. Permintaan blob akan gagal ketika tag blob tidak cocok dengan ekspresi tertentu. Lihat detail di https://docs.microsoft.com/en-us/rest/api/storageservices/specifying-conditional-headers-for-blob-service-operations#tags-conditional-operations.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Azure. Storage. Blobs.Specialized.BlobBaseClient

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageBlob

## CATATAN

## RELATED LINKS
