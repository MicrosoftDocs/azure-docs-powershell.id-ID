---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstorageblobbytag
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageBlobByTag.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageBlobByTag.md
ms.openlocfilehash: 13db73a2fe9037f2805991d8727ffcc4400e7823
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143271341"
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
Cmdlet **Get-AzStorageBlobByTag** mencantumkan blob dalam akun penyimpanan di seluruh wadah, dengan ekspresi sql filter tag blob.

## EXAMPLES

### Contoh 1: Cantumkan semua blob yang cocok dengan tag blob tertentu, di seluruh kontainer.
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

Perintah ini mencantumkan semua blob dalam accoun penyimpanan, yang berisi tag dengan nama "tag1" dan nilai "value1".

### Contoh 2: Blob daftar dalam wadah tertentu dan cocok dengan tag blob tertentu
```
PS C:\> Get-AzStorageBlobByTag -TagFilterSqlExpression "@container='containername' AND ""tag1""='value1'" -Context $ctx

   AccountName: storageaccountname, ContainerName: containername

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
test1                                                                                                                                      False                                    
test2                                                                                                                                      False
```

Perintah ini mencantumkan blob dalam wadah dan cocok dengan tag blob tertentu.

### Contoh 3: Cantumkan semua blob yang cocok dengan tag blob tertentu, di seluruh wadah, dan dapatkan properti blob.
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

Perintah ini mencantumkan semua blob dalam accoun penyimpanan, yang berisi tag dengan nama "tag1" dan nilai "value1", dan mendapatkan properti blob.
Harap diperhatikan, untuk mendapatkan properti blob dengan parameter -GetBlobProperty, setiap blob akan memerlukan permintaan tambahan, sehingga cmdlet berjalan menunjukkan ketika ada banyak blob.

## PARAMETERS

### -ClientTimeoutPerRequest
Waktu eksekusi maksimum sisi klien untuk setiap permintaan dalam hitung detik.

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
Jumlah total tugas asinkron serentak.
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

### -Konteks
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
Karena blob yang didapatkan dengan tag tidak berisi proeprties blob, tentukan parameter tis untuk mendapatkan properti blob dengan permintaan tambahan pada setiap blob.

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
Jumlah maksimal dari blob yang dapat kembali.

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

### -TagFilterSqlExpression
Memfilter kumpulan hasil agar hanya menyertakan blob yang tagnya cocok dengan ekspresi tertentu.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageBlob

## NOTES

## RELATED LINKS
