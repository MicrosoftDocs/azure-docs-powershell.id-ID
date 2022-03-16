---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: E54BFD3A-CD54-4E6B-9574-92B8D3E88FF3
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstorageblob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageBlob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageBlob.md
ms.openlocfilehash: 36ac3040ba82bb5d504c3cd327846de77dbf8667
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139998312"
---
# Get-AzStorageBlob

## SYNOPSIS
Mencantumkan blob dalam wadah.

## SYNTAX

### BlobName (Default)
```
Get-AzStorageBlob [[-Blob] <String>] [-Container] <String> [-IncludeDeleted] [-IncludeTag] [-MaxCount <Int32>]
 [-ContinuationToken <BlobContinuationToken>] [-TagCondition <String>] [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

### SingleBlobSnapshotTime
```
Get-AzStorageBlob [-Blob] <String> [-Container] <String> [-IncludeDeleted] [-IncludeTag]
 -SnapshotTime <DateTimeOffset> [-MaxCount <Int32>] [-ContinuationToken <BlobContinuationToken>]
 [-TagCondition <String>] [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [<CommonParameters>]
```

### SingleBlobVersionID
```
Get-AzStorageBlob [-Blob] <String> [-Container] <String> [-IncludeDeleted] [-IncludeTag] -VersionId <String>
 [-MaxCount <Int32>] [-ContinuationToken <BlobContinuationToken>] [-TagCondition <String>]
 [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

### BlobPrefix
```
Get-AzStorageBlob [-Prefix <String>] [-Container] <String> [-IncludeDeleted] [-IncludeVersion] [-IncludeTag]
 [-MaxCount <Int32>] [-ContinuationToken <BlobContinuationToken>] [-Context <IStorageContext>]
 [-ServerTimeoutPerRequest <Int32>] [-ClientTimeoutPerRequest <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzStorageBlob** mencantumkan blob dalam wadah tertentu dalam akun penyimpanan Azure.

## EXAMPLES

### Contoh 1: Get a blob by blob name
```
PS C:\>Get-AzStorageBlob -Container "ContainerName" -Blob blob*
```

Perintah ini menggunakan nama blob dan wildcard untuk mendapatkan blob.

### Contoh 2: Get blobs in a container by using the pipeline
```
PS C:\>Get-AzStorageContainer -Name container* | Get-AzStorageBlob -IncludeDeleted

   Container Uri: https://storageaccountname.blob.core.windows.net/container1

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime         IsDeleted 
----                 --------  ------          -----------                    ------------         ---------- ------------         --------- 
test1                BlockBlob 403116          application/octet-stream       2017-11-08 07:53:19Z            2017-11-08 08:19:32Z True      
test1                BlockBlob 403116          application/octet-stream       2017-11-08 09:00:29Z                                 True      
test2                BlockBlob 403116          application/octet-stream       2017-11-08 07:53:00Z                                 False
```

Perintah ini menggunakan pipeline untuk mendapatkan semua blob (termasuk blob dalam status Dihapus) dalam wadah.

### Contoh 3: Mendapatkan prefiks blob menurut nama
```
PS C:\>Get-AzStorageBlob -Container "ContainerName" -Prefix "blob"
```

Perintah ini menggunakan prefiks nama untuk mendapatkan blob.

### Contoh 4: List blobs in multiple batches
```
PS C:\>$MaxReturn = 10000
PS C:\> $ContainerName = "abc"
PS C:\> $Total = 0
PS C:\> $Token = $Null
PS C:\> do
 {
     $Blobs = Get-AzStorageBlob -Container $ContainerName -MaxCount $MaxReturn  -ContinuationToken $Token
     $Total += $Blobs.Count
     if($Blobs.Length -le 0) { Break;}
     $Token = $Blobs[$blobs.Count -1].ContinuationToken;
 }
 While ($null -ne $Token)
PS C:\> Echo "Total $Total blobs in container $ContainerName"
```

Contoh ini menggunakan *parameter MaxCount* dan *ContinuationToken* untuk Azure Storage blob dalam beberapa kumpulan.
Empat perintah pertama menetapkan nilai ke variabel untuk digunakan dalam contoh.
Perintah kelima menentukan pernyataan **Do-While** yang menggunakan cmdlet **Get-AzStorageBlob** untuk mendapatkan blob.
Pernyataan menyertakan token kelanjutan yang disimpan dalam variabel $Token disimpan.
$Token perubahan saat pengulangan berjalan.
Untuk informasi selengkapnya, ketik `Get-Help About_Do`.
Perintah final menggunakan perintah **Echo** untuk menampilkan total.

### Contoh 5: Get all blobs in a container include blob version
```
PS C:\>Get-AzStorageBlob -Container "containername"  -IncludeVersion 

   AccountName: storageaccountname, ContainerName: containername

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
blob1                BlockBlob 2097152         application/octet-stream       2020-07-06 06:56:06Z Hot                                     False      2020-07-06T06:56:06.2432658Z  
blob1                BlockBlob 2097152         application/octet-stream       2020-07-06 06:56:06Z Hot        2020-07-06T06:56:06.8588431Z False                                    
blob1                BlockBlob 2097152         application/octet-stream       2020-07-06 06:56:06Z Hot                                     False      2020-07-06T06:56:06.8598431Z *  
blob2                BlockBlob 2097152         application/octet-stream       2020-07-03 16:19:16Z Hot                                     False      2020-07-03T16:19:16.2883167Z  
blob2                BlockBlob 2097152         application/octet-stream       2020-07-03 16:19:35Z Hot                                     False      2020-07-03T16:19:35.2381110Z *
```

Perintah ini akan memasukkan semua blob dalam wadah yang menyertakan versi blob.

### Contoh 6: Mendapatkan versi blob tunggal
```
PS C:\> Get-AzStorageBlob -Container "containername" -Blob blob2 -VersionId "2020-07-03T16:19:16.2883167Z" 

   AccountName: storageaccountname, ContainerName: containername

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
blob2                BlockBlob 2097152         application/octet-stream       2020-07-03 16:19:16Z Hot                                     False      2020-07-03T16:19:16.2883167Z
```

Perintah ini akan mendapatkan versi blob tunggal dengan VersionId.

### Contoh 7: Mendapatkan snapshot blob tunggal
```
PS C:\> Get-AzStorageBlob -Container "containername" -Blob blob1 -SnapshotTime "2020-07-06T06:56:06.8588431Z"

   AccountName: storageaccountname, ContainerName: containername

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
blob1                BlockBlob 2097152         application/octet-stream       2020-07-06 06:56:06Z Hot        2020-07-06T06:56:06.8588431Z False
```

Perintah ini mendapatkan snapshot blob tunggal dengan SnapshotTime.

### Contoh 8: Get blob include blob tags
```
PS C:\> $blobs = Get-AzStorageBlob -Container "containername" -IncludeTag

PS C:\> $blobs

   AccountName: storageaccountname, ContainerName: containername

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
testblob             BlockBlob 2097152         application/octet-stream       2020-07-23 09:35:02Z Hot                                     False      2020-07-23T09:35:02.8527357Z *
testblob2            BlockBlob 2097152         application/octet-stream       2020-07-23 09:35:04Z Hot                                     False      2020-07-23T09:35:04.0856187Z *


PS C:\> $blobs[0].Tags
Name          Value 
----          -----
tag1          value1
tag2          value2
```

Perintah ini mencantumkan blob dari wadah dengan tag blob, dan memperlihatkan tag blob pertama.

### Contoh 9: Get a single blob with blob tag condition
```
PS C:\> Get-AzStorageBlob -Container "containername" -Blob testblob -TagCondition """tag1""='value1'"

   AccountName: storageaccountname, ContainerName: containername

Name                 BlobType  Length          ContentType                    LastModified         AccessTier SnapshotTime                 IsDeleted  VersionId                     
----                 --------  ------          -----------                    ------------         ---------- ------------                 ---------  ---------                     
testblob             BlockBlob 2097152         application/octet-stream       2020-07-23 09:35:02Z Hot                                     False      2020-07-23T09:35:02.8527357Z *
```

Perintah ini mendapatkan satu blob dengan kondisi tag blob. Cmdlet hanya akan berhasil jika blob berisi tag dengan nama "tag1" dan nilai "value1", cmdlet lain akan gagal dengan kode kesalahan 412.

## PARAMETERS

### -Blob
Menentukan pola nama atau nama, yang dapat digunakan untuk pencarian wildcard.
Jika tidak ada nama blob yang ditentukan, cmdlet akan mencantumkan semua blob dalam wadah yang ditentukan.
Jika nilai ditentukan untuk parameter ini, cmdlet akan mencantumkan semua blob dengan nama yang cocok dengan parameter ini. Parameter ini mendukung wildcard di mana saja dalam string.

```yaml
Type: System.String
Parameter Sets: BlobName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

```yaml
Type: System.String
Parameter Sets: SingleBlobSnapshotTime, SingleBlobVersionID
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ClientTimeoutPerRequest
Menentukan interval waktu yang habis di sisi klien, dalam hitungan detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini mencoba permintaan.
Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini akan mengembalikan kesalahan.

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
Menentukan jumlah maksimum panggilan jaringan bersama.
Anda dapat menggunakan parameter ini untuk membatasi konkurensi guna membatasi penggunaan CPU lokal dan bandwidth dengan menentukan jumlah maksimum panggilan jaringan bersamaan.
Nilai yang ditentukan adalah hitungan absolut dan tidak dikalikan dengan hitungan inti.
Parameter ini bisa membantu mengurangi masalah koneksi jaringan di lingkungan bandwidth yang rendah, seperti 100 kilobit per detik.
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
Menentukan nama wadah.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: N, Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konteks
Menentukan akun penyimpanan Azure yang ingin Anda dapatkan daftar blobnya.
Anda dapat menggunakan cmdlet New-AzStorageContext tersebut untuk membuat konteks penyimpanan.

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
Menentukan token lanjutan untuk daftar blob.
Gunakan parameter ini dan parameter *MaxCount* untuk mencantumkan blob dalam beberapa kumpulan.

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

### -IncludeDeleted
Sertakan Blob Dihapus, secara default get blob tidak akan menyertakan blob terhapus.

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

### -IncludeTag
Menyertakan tag blob, secara default tag blob tidak akan menyertakan tag blob.

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

### -IncludeVersion
Versi Blob hanya akan tercantum jika parameter ini ada, secara default akan mendapatkan blob tidak akan menyertakan versi blob.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: BlobPrefix
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxCount
Menentukan jumlah maksimum objek yang dikembalikan cmdlet ini.

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

### -Prefix
Menentukan prefiks untuk nama blob yang ingin Anda dapatkan.
Parameter ini tidak mendukung penggunaan ekspresi reguler atau karakter wildcard untuk pencarian.
Artinya, jika wadah hanya memiliki blob bernama "My", "MyBlob1", dan "MyBlob2" dan Anda menentukan "-Prefix My*", cmdlet tidak akan mengembalikan blob.
Namun, jika Anda menentukan "-Prefiks Saya", cmdlet akan mengembalikan "My", "MyBlob1", dan "MyBlob2".

```yaml
Type: System.String
Parameter Sets: BlobPrefix
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Menentukan interval waktu habis di sisi layanan, dalam detik, untuk permintaan.
Jika interval yang ditentukan berlalu sebelum layanan memproses permintaan, layanan penyimpanan mengembalikan kesalahan.

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

### -SnapshotTime
Blob SnapshotTime

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: SingleBlobSnapshotTime
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TagCondition
Pernyataan ekspresi Tag opsional untuk memeriksa kecocokan kondisi. Permintaan blob akan gagal ketika tag blob tidak cocok dengan ekspresi tertentu.
Lihat detail di https://docs.microsoft.com/en-us/rest/api/storageservices/specifying-conditional-headers-for-blob-service-operations#tags-conditional-operations.

```yaml
Type: System.String
Parameter Sets: BlobName, SingleBlobSnapshotTime, SingleBlobVersionID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VersionId
Blob VersionId

```yaml
Type: System.String
Parameter Sets: SingleBlobVersionID
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

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.commands.common. Storage. ResourceModel.AzureStorageBlob

## CATATAN

## RELATED LINKS

[Get-AzStorageBlobContent](./Get-AzStorageBlobContent.md)

[Remove-AzStorageBlob](./Remove-AzStorageBlob.md)

[Set-AzStorageBlobContent](./Set-AzStorageBlobContent.md)


