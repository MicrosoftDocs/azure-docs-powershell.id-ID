---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
Module Name: Azure.Storage
ms.assetid: E54BFD3A-CD54-4E6B-9574-92B8D3E88FF3
online version: https://docs.microsoft.com/en-us/powershell/module/azure.storage/get-azurestorageblob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/Get-AzureStorageBlob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/Get-AzureStorageBlob.md
ms.openlocfilehash: da3b5f969bfa8beafab20f256df237588ed87048
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420889"
---
# Get-AzureStorageBlob

## SYNOPSIS
Mencantumkan blob dalam wadah.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### BlobName (Default)
```
Get-AzureStorageBlob [[-Blob] <String>] [-Container] <String> [-IncludeDeleted] [-MaxCount <Int32>]
 [-ContinuationToken <BlobContinuationToken>] [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

### BlobPrefix
```
Get-AzureStorageBlob [-Prefix <String>] [-Container] <String> [-IncludeDeleted] [-MaxCount <Int32>]
 [-ContinuationToken <BlobContinuationToken>] [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-ConcurrentTaskCount <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorageBlob** mencantumkan blob dalam wadah tertentu dalam akun penyimpanan Azure.

## EXAMPLES

### Contoh 1: Get a blob by blob name
```
PS C:\>Get-AzureStorageBlob -Container "ContainerName" -Blob blob*
```

Perintah ini menggunakan nama blob dan wildcard untuk mendapatkan blob.

### Contoh 2: Get blobs in a container by using the pipeline
```
PS C:\>Get-AzureStorageContainer -Name container* | Get-AzureStorageBlob -IncludeDeleted

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
PS C:\>Get-AzureStorageBlob -Container "ContainerName" -Prefix "blob"
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
     $Blobs = Get-AzureStorageBlob -Container $ContainerName -MaxCount $MaxReturn  -ContinuationToken $Token
     $Total += $Blobs.Count
     if($Blobs.Length -le 0) { Break;}
     $Token = $Blobs[$blobs.Count -1].ContinuationToken;
 }
 While ($Token -ne $Null)
PS C:\> Echo "Total $Total blobs in container $ContainerName"
```

Contoh ini menggunakan *parameter MaxCount* dan *ContinuationToken* untuk Azure Storage blob dalam beberapa kumpulan.
Empat perintah pertama menetapkan nilai ke variabel untuk digunakan dalam contoh.

Perintah kelima menentukan pernyataan **Do-While** yang menggunakan cmdlet **Get-AzureStorageBlob** untuk mendapatkan blob.
Pernyataan menyertakan token lanjutan yang disimpan dalam variabel $Token.
$Token perubahan saat pengulangan berjalan.
Untuk informasi selengkapnya, ketik `Get-Help About_Do` .

Perintah final menggunakan perintah **Echo** untuk menampilkan total.

## PARAMETERS

### -Blob
Menentukan pola nama atau nama, yang dapat digunakan untuk pencarian wildcard.
Jika tidak ada nama blob yang ditentukan, cmdlet akan mencantumkan semua blob dalam wadah yang ditentukan.
Jika nilai ditentukan untuk parameter ini, cmdlet akan mencantumkan semua blob dengan nama yang cocok dengan parameter ini.

```yaml
Type: String
Parameter Sets: BlobName
Aliases: 

Required: False
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
Type: Int32
Parameter Sets: (All)
Aliases: 

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
Type: Int32
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
Type: String
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
Anda dapat menggunakan cmdlet New-AzureStorageContext untuk membuat konteks penyimpanan.

```yaml
Type: IStorageContext
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
Type: BlobContinuationToken
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeDeleted
Sertakan Blob Dihapus, secara default get blob tidak akan menyertakan blob terhapus.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
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
Type: Int32
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
Type: String
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
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### IStorageContext
Parameter 'Konteks' menerima nilai tipe 'IStorageContext' dari saluran

## OUTPUTS

### AzureStorageBlob

## CATATAN

## RELATED LINKS

[Get-AzureStorageBlobContent](./Get-AzureStorageBlobContent.md)

[Remove-AzureStorageBlob](./Remove-AzureStorageBlob.md)

[Set-AzureStorageBlobContent](./Set-AzureStorageBlobContent.md)


