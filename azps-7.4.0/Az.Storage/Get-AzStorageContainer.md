---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 90C3DF13-0010-49B6-A8CD-C6AC34BC3EFA
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstoragecontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageContainer.md
ms.openlocfilehash: b6497d67b1041da6038b2e5cbf4550b182de1a86
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142864486"
---
# Get-AzStorageContainer

## SYNOPSIS
Mencantumkan wadah penyimpanan.

## SYNTAX

### ContainerName (Default)
```
Get-AzStorageContainer [[-Name] <String>] [-MaxCount <Int32>] [-ContinuationToken <BlobContinuationToken>]
 [-IncludeDeleted] [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [<CommonParameters>]
```

### ContainerPrefix
```
Get-AzStorageContainer -Prefix <String> [-MaxCount <Int32>] [-ContinuationToken <BlobContinuationToken>]
 [-IncludeDeleted] [-Context <IStorageContext>] [-ServerTimeoutPerRequest <Int32>]
 [-ClientTimeoutPerRequest <Int32>] [-DefaultProfile <IAzureContextContainer>] [-ConcurrentTaskCount <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzStorageContainer** mencantumkan wadah penyimpanan yang terkait dengan akun penyimpanan di Azure.

## EXAMPLES

### Contoh 1: Dapatkan wadah Azure Storage menurut nama
```
PS C:\>Get-AzStorageContainer -Name container*
```

Contoh ini menggunakan karakter wildcard untuk mengembalikan daftar semua wadah dengan nama yang dimulai dengan wadah.

### Contoh 2: Dapatkan kontainer Azure Storage menurut prefiks nama kontainer
```
PS C:\>Get-AzStorageContainer -Prefix "container"
```

Contoh ini menggunakan parameter *Prefiks* untuk mengembalikan daftar semua kontainer dengan nama yang dimulai dengan kontainer.

### Contoh 3: Wadah Azure Storage daftar, sertakan wadah yang dihapus
```
PS C:\> $containers =  Get-AzStorageContainer -IncludeDeleted -Context $ctx 

PS C:\> $containers

   Storage Account Name: storageaccountname

Name                 PublicAccess         LastModified                   IsDeleted  VersionId                                                                                                                                                                                                                                                      
----                 ------------         ------------                   ---------  ---------                                                                                                                                                                   
testcon              Off                  8/28/2020 10:18:13 AM +00:00                                                                                                                                                                                                                                                                   
testcon2                                  9/4/2020 12:52:37 PM +00:00    True       01D67D248986B6DA  

PS C:\> $c[1].BlobContainerProperties

LastModified                   : 9/4/2020 12:52:37 PM +00:00
LeaseStatus                    : Unlocked
LeaseState                     : Expired
LeaseDuration                  : 
PublicAccess                   : 
HasImmutabilityPolicy          : False
HasLegalHold                   : False
DefaultEncryptionScope         : $account-encryption-key
PreventEncryptionScopeOverride : False
DeletedOn                      : 9/8/2020 4:29:59 AM +00:00
RemainingRetentionDays         : 299
ETag                           : "0x8D850D167059285"
Metadata                       : {}
```

Contoh ini mencantumkan semua wadah akun penyimpanan, termasuk wadah yang dihapus.
Lalu perlihatkan properti kontainer yang dihapus, termasuk : DeletedOn, RemainingRetentionDays.
Kontainer yang dihapus hanya akan ada setelah softdelete Container yang diaktifkan dengan Enable-AzStorageBlobDeleteRetentionPolicy.

## PARAMETERS

### -ClientTimeoutPerRequest
Menentukan interval waktu habis pihak klien, dalam hitungan detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini akan mencoba kembali permintaan.
Jika cmdlet ini tidak menerima respons yang berhasil sebelum interval berlalu, cmdlet ini mengembalikan kesalahan.

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
Menentukan maksimum panggilan jaringan serentak.
Anda bisa menggunakan parameter ini untuk membatasi konkurensi untuk membatasi penggunaan CPU lokal dan bandwidth dengan menentukan jumlah maksimum panggilan jaringan bersamaan.
Nilai yang ditentukan adalah hitungan absolut dan tidak dikalikan dengan hitungan inti.
Parameter ini dapat membantu mengurangi masalah koneksi jaringan di lingkungan bandwidth rendah, seperti 100 kilobit per detik.
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
Menentukan konteks penyimpanan.
Untuk membuatnya, Anda bisa menggunakan cmdlet New-AzStorageContext.
Izin kontainer tidak akan diambil ketika Anda menggunakan konteks penyimpanan yang dibuat dari SAS Token, karena izin kontainer kueri memerlukan izin kunci akun Storage.

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
Menentukan token kelanjutan untuk daftar blob.

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
Sertakan wadah yang dihapus, secara default wadah daftar tidak akan menyertakan kontainer yang dihapus

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

### -Nama
Menentukan nama wadah.
Jika nama wadah kosong, cmdlet mencantumkan semua wadah.
Jika tidak, daftar semua wadah yang cocok dengan nama yang ditentukan atau pola nama reguler.

```yaml
Type: System.String
Parameter Sets: ContainerName
Aliases: N, Container

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Prefiks
Menentukan prefiks yang digunakan dalam nama wadah atau wadah yang ingin Anda dapatkan.
Anda dapat menggunakan ini untuk menemukan semua wadah yang dimulai dengan string yang sama, seperti "saya" atau "uji".

```yaml
Type: System.String
Parameter Sets: ContainerPrefix
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerTimeoutPerRequest
Menentukan interval batas waktu sisi layanan, dalam detik, untuk permintaan.
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Common.Authentication.Abstractions.IStorageContext

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Common. Storage. ResourceModel.AzureStorageContainer

## NOTES

## RELATED LINKS

[New-AzStorageContainer](./New-AzStorageContainer.md)

[Hapus-AzStorageContainer](./Remove-AzStorageContainer.md)

[Set-AzStorageContainerAcl](./Set-AzStorageContainerAcl.md)


