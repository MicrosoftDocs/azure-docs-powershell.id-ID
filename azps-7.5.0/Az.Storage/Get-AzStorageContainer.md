---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.dll-Help.xml
Module Name: Az.Storage
ms.assetid: 90C3DF13-0010-49B6-A8CD-C6AC34BC3EFA
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstoragecontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageContainer.md
ms.openlocfilehash: b6497d67b1041da6038b2e5cbf4550b182de1a86
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144193642"
---
# Get-AzStorageContainer

## SYNOPSIS
Mencantumkan kontainer penyimpanan.

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
Cmdlet **Get-AzStorageContainer** mencantumkan kontainer penyimpanan yang terkait dengan akun penyimpanan di Azure.

## EXAMPLES

### Contoh 1: Dapatkan kontainer Azure Storage berdasarkan nama
```
PS C:\>Get-AzStorageContainer -Name container*
```

Contoh ini menggunakan karakter kartubebas untuk mengembalikan daftar semua kontainer dengan nama yang dimulai dengan kontainer.

### Contoh 2: Dapatkan kontainer Azure Storage menurut awalan nama kontainer
```
PS C:\>Get-AzStorageContainer -Prefix "container"
```

Contoh ini menggunakan parameter *Awalan* untuk mengembalikan daftar semua kontainer dengan nama yang dimulai dengan kontainer.

### Contoh 3: Mencantumkan kontainer Azure Storage, termasuk kontainer yang dihapus
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

Contoh ini mencantumkan semua kontainer akun penyimpanan, termasuk kontainer yang dihapus.
Kemudian tampilkan properti kontainer yang dihapus, termasuk : DeletedOn, RemainingRetentionDays.
Kontainer yang dihapus hanya akan ada setelah softdelete Kontainer yang diaktifkan dengan Enable-AzStorageBlobDeleteRetentionPolicy.

## PARAMETERS

### -ClientTimeoutPerRequest
Menentukan interval waktu habis sisi klien, dalam hitungan detik, untuk satu permintaan layanan.
Jika panggilan sebelumnya gagal dalam interval yang ditentukan, cmdlet ini mencoba kembali permintaan.
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
Menentukan panggilan jaringan bersamaan maksimum.
Anda dapat menggunakan parameter ini untuk membatasi konkurensi untuk membatasi penggunaan CPU dan bandwidth lokal dengan menentukan jumlah maksimum panggilan jaringan bersamaan.
Nilai yang ditentukan adalah jumlah absolut dan tidak dikalikan dengan jumlah inti.
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

### -Context
Menentukan konteks penyimpanan.
Untuk membuatnya, Anda dapat menggunakan cmdlet New-AzStorageContext.
Izin kontainer tidak akan diambil saat Anda menggunakan konteks penyimpanan yang dibuat dari Token SAS, karena izin kontainer kueri memerlukan izin kunci akun Storage.

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
Menyertakan kontainer yang dihapus, secara default, kontainer daftar tidak akan menyertakan kontainer yang dihapus

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

### -Name
Menentukan nama kontainer.
Jika nama kontainer kosong, cmdlet mencantumkan semua kontainer.
Jika tidak, ini mencantumkan semua kontainer yang cocok dengan nama yang ditentukan atau pola nama reguler.

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

### -Awalan
Menentukan awalan yang digunakan dalam nama kontainer atau kontainer yang ingin Anda dapatkan.
Anda dapat menggunakan ini untuk menemukan semua kontainer yang dimulai dengan string yang sama, seperti "my" atau "test".

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
Menentukan interval waktu habis sisi layanan, dalam detik, untuk permintaan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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


