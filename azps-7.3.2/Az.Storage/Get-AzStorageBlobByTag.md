---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstorageblobbytag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageBlobByTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageBlobByTag.md
ms.openlocfilehash: 13db73a2fe9037f2805991d8727ffcc4400e7823
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140385287"
---
# Get-AzStorageBlobByTag

## SYNOPSIS
Mencantumkan blob dalam akun penyimpanan di seluruh wadah, dengan ekspresi sql filter tag blob.

## SYNTAX

```
Get-AzStorageBlobByTag -TagFilterSqlExpression <String> [-MaxCount <Int32>]
 [-ContinuationToken <BlobContinuationToken>] [-GetBlobProperty] [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzStorageBlobByTag** mencantumkan blob dalam akun penyimpanan di seluruh wadah, dengan filter tag blob ekspresi sql.

## EXAMPLES

### Contoh 1: List all blobs match a specific blob tag, across containers.
```
PS C:\> Get-AzStorageBlobByTag -TagFilterSqlExpression """tag1""='value1'" -Context $ctx 

   AccountName: storageaccountname, ContainerName: containername1

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
testblob                                                                                                                                   False                                    
testblob2                                                                                                                                  False                                    

   AccountName: storageaccountname, ContainerName: containername2

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
testblob3                                                                                                                                   False                                    
testblob4                                                                                                                                   False
```

Perintah ini mencantumkan semua blob dalam akun penyimpanan, yang berisi tag dengan nama "tag1" dan nilai "nilai1".

### Contoh 2: Daftar blob dalam wadah tertentu dan cocok dengan tag blob tertentu
```
PS C:\> Get-AzStorageBlobByTag -TagFilterSqlExpression "@container='containername' AND ""tag1""='value1'" -Context $ctx

   AccountName: storageaccountname, ContainerName: containername

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
test1                                                                                                                                      False                                    
test2                                                                                                                                      False
```

Perintah ini mencantumkan blob dalam wadah dan sesuai dengan tag blob tertentu.

### Contoh 3: Daftar semua blob cocok dengan tag blob tertentu, seluruh wadah, dan mendapatkan properti blob.
```
PS C:\> Get-AzStorageBlobByTag -TagFilterSqlExpression """tag1""='value1'" -GetBlobProperty

   AccountName: storageaccountname, ContainerName: containername1

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
testblob             BlockBlob 2097152         application/octet-stream       2020-07-23 09:35:02Z Hot                                     False      2020-07-23T09:35:02.8527357Z *                                   
testblob2            BlockBlob 1048012         application/octet-stream       2020-07-23 09:35:05Z Hot                                     False      2020-07-23T09:35:05.2504530Z *                             

   AccountName: storageaccountname, ContainerName: containername2

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
testblob3            BlockBlob 100             application/octet-stream       2020-07-01 09:55:14Z Hot                                     False      2020-07-01T09:55:14.6507341Z *                      
testblob4            BlockBlob 2024            application/octet-stream       2020-07-01 09:42:11Z Hot                                     False      2020-07-01T09:42:11.4283807Z *
```

Perintah ini mencantumkan semua blob dalam akun penyimpanan, yang berisi tag dengan nama "tag1" dan nilai "nilai1", serta mendapatkan properti blob.
Perlu diingat, untuk mendapatkan properti blob dengan parameter -GetBlobProperty, setiap blob memerlukan permintaan tambahan, sehingga cmdlet berjalan ketika terdapat banyak blob.

## PARAMETERS

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

### -ContinuationToken
Token Kelanjutan.

```yaml
Type: Microsoft.Azure.Storage.Blob.BlobContinuationToken
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
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GetBlobProperty
Karena tag dapatkan oleh blob tidak berisi blob proeprties, tentukan parameter tis untuk mendapatkan properti blob dengan permintaan tambahan di setiap blob.

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

### -MaxCount
Jumlah maks blob yang dapat dikembalikan.

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

### -TagFilterSqlExpression
Memfilter kumpulan hasil yang diatur hanya untuk menyertakan blob yang tagnya cocok dengan ekspresi yang ditentukan.
Lihat detail di https://docs.microsoft.com/en-us/rest/api/storageservices/find-blobs-by-tags#remarks.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.commands.common. Storage. ResourceModel.AzureStorageBlob

## CATATAN

## RELATED LINKS
