---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/set-azstorageblobtag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageBlobTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Set-AzStorageBlobTag.md
ms.openlocfilehash: 46be83ac24490f73fc37063fa3c365e314a99875
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136165233"
---
# Set-AzStorageBlobTag

## SYNOPSIS
Mengatur tag blob tertentu blob.

## SYNTAX

### NamePipeline (Default)
```
Set-AzStorageBlobTag [-Blob] <String> [-Container] <String> -Tag <Hashtable> [-TagCondition <String>]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### BlobPipeline
```
Set-AzStorageBlobTag -BlobBaseClient <BlobBaseClient> -Tag <Hashtable> [-TagCondition <String>]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ContainerPipeline
```
Set-AzStorageBlobTag -CloudBlobContainer <CloudBlobContainer> [-Blob] <String> -Tag <Hashtable>
 [-TagCondition <String>] [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Set-AzStorageBlobTag** mengatur tag blob tertentu blob.

## EXAMPLES

### Contoh 1: Mengatur tag blob di blob tertentu
```
PS C:\> Set-AzStorageBlobTag -Container "containername" -Blob testblob -Tag @{"tag1" = "value1"; "tag2" = "value2" }

Name                           Value                                                                                                                                                                                 
----                           -----                                                                                                                                                                                 
tag2                           value2                                                                                                                                                                                
tag1                           value1
```

Perintah ini mengatur tag blob tertentu di blob tertentu.

### Contoh 2: Mengatur tag blob pada blob tertentu dengan kondisi tag
```
PS C:\> Set-AzStorageBlobTag -Container "containername" -Blob testblob -Tag @{"tag1" = "value1"; "tag2" = "value2" } -TagCondition """tag1""='value1'"

Name                           Value                                                                                                                                                                                 
----                           -----                                                                                                                                                                                 
tag2                           value2                                                                                                                                                                                
tag1                           value1
```

Perintah ini mengatur tag blob pada blob tertentu dengan kondisi tag.
Cmdlet hanya akan berhasil jika blob berisi tag dengan nama "tag1" dan nilai "value1", cmdlet lain akan gagal dengan kode kesalahan 412.

## PARAMETERS

### -Blob
Nama Blob

```yaml
Type: System.String
Parameter Sets: NamePipeline, ContainerPipeline
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
Waktu eksekusi maksimal sisi klien untuk setiap permintaan dalam detik.

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

### -CloudBlobContainer
Objek CloudBlobContainer

```yaml
Type: Microsoft.Azure.Storage.Blob.CloudBlobContainer
Parameter Sets: ContainerPipeline
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConcurrentTaskCount
Jumlah total tugas bersama.
Nilai default adalah 10.

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

### -Container
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

### -Konteks
Azure Storage Konteks

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

### -ServerTimeoutPerRequest
Waktu server habis untuk setiap permintaan dalam hitungan detik.

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

### -Tag
tag Blob yang akan diatur ke blob.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TagCondition
Pernyataan ekspresi Tag opsional untuk memeriksa kecocokan kondisi. Permintaan blob akan gagal ketika tag blob tidak cocok dengan ekspresi tertentu.
Lihat detail di https://docs.microsoft.com/en-us/rest/api/storageservices/specifying-conditional-headers-for-blob-service-operations#tags-conditional-operations .

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Azure. Storage. Blobs.Specialized.BlobBaseClient

### Microsoft.Azure. Storage. Blob.CloudBlobContainer

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
