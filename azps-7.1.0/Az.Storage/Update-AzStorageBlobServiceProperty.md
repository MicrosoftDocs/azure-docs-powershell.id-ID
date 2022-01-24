---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/update-azstorageblobserviceproperty
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Update-AzStorageBlobServiceProperty.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Update-AzStorageBlobServiceProperty.md
ms.openlocfilehash: 811211e0cb70729fa59a2221128e15f6200ed18a
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136712380"
---
# Update-AzStorageBlobServiceProperty

## SYNOPSIS
Mengubah properti layanan untuk layanan Azure Storage Blob.

## SYNTAX

### Nama Akun (Default)
```
Update-AzStorageBlobServiceProperty [-ResourceGroupName] <String> [-StorageAccountName] <String>
 [-DefaultServiceVersion <String>] [-EnableChangeFeed <Boolean>] [-ChangeFeedRetentionInDays <Int32>]
 [-IsVersioningEnabled <Boolean>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AccountObject
```
Update-AzStorageBlobServiceProperty -StorageAccount <PSStorageAccount> [-DefaultServiceVersion <String>]
 [-EnableChangeFeed <Boolean>] [-ChangeFeedRetentionInDays <Int32>] [-IsVersioningEnabled <Boolean>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BlobServicePropertiesResourceId
```
Update-AzStorageBlobServiceProperty [-ResourceId] <String> [-DefaultServiceVersion <String>]
 [-EnableChangeFeed <Boolean>] [-ChangeFeedRetentionInDays <Int32>] [-IsVersioningEnabled <Boolean>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzStorageBlobServiceProperty** mengubah properti layanan untuk layanan Azure Storage Blob.

## EXAMPLES

### Contoh 1: Mengatur layanan Blob DefaultServiceVersion ke 2018-03-28
```
C:\PS> Update-AzStorageBlobServiceProperty -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -DefaultServiceVersion 2018-03-28 

StorageAccountName            : mystorageaccount
ResourceGroupName             : myresourcegroup
DefaultServiceVersion         : 2018-03-28
DeleteRetentionPolicy.Enabled : False
DeleteRetentionPolicy.Days    : 
RestorePolicy.Enabled         : 
RestorePolicy.Days            : 
ChangeFeed.Enabled            : 
ChangeFeed.RetentionInDays    :
IsVersioningEnabled           :
```

Perintah ini mengatur DefaultServiceVersion Layanan Blob ke 2018-03-28.

### Contoh 2: Aktifkan Changefeed on Blob service of a Storage account with ChangeFeedRetentionInDays as 5 days
```
C:\PS> Update-AzStorageBlobServiceProperty -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -EnableChangeFeed $true -ChangeFeedRetentionInDays 5

StorageAccountName            : mystorageaccount
ResourceGroupName             : myresourcegroup
DefaultServiceVersion         : 
DeleteRetentionPolicy.Enabled : False
DeleteRetentionPolicy.Days    : 
RestorePolicy.Enabled         : 
RestorePolicy.Days            : 
ChangeFeed.Enabled            : True
ChangeFeed.RetentionInDays    : 5
IsVersioningEnabled           :
```

Perintah ini mengaktifkan Changefeed di layanan Blob akun Storage dengan ChangeFeedRetentionInDays sebagai 5 hari.
Ubah dukungan umpan di Azure Blob Storage berfungsi dengan mendengarkan akun penyimpanan GPv2 atau Blob untuk setiap kejadian penghapusan, modifikasi, atau pembuatan tingkat blob. Kemudian, membuat log kejadian yang diurutkan untuk blob yang disimpan dalam wadah $blobchangefeed dalam akun penyimpanan. The serialized changes are persisted as an Apache Avro file and can be processed asynchronously and incrementally.
Jika tidak menentukan ChangeFeedRetentionInDays, akan mendapatkan nilai null dalam properti layanan, menunjukkan penyimpanan umpan perubahan yang tidak terbatas.

### Contoh 3: Mengaktifkan Versioning di layanan Blob Storage pengguna
```
C:\PS> Update-AzStorageBlobServiceProperty -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount" -IsVersioningEnabled $true

StorageAccountName            : mystorageaccount
ResourceGroupName             : myresourcegroup
DefaultServiceVersion         : 
DeleteRetentionPolicy.Enabled : False
DeleteRetentionPolicy.Days    : 
RestorePolicy.Enabled         : 
RestorePolicy.Days            : 
ChangeFeed                    : 
ChangeFeed.RetentionInDays    :
IsVersioningEnabled           : True
```

Perintah ini mengaktifkan Versi pada layanan Blob akun Storage pengguna

## PARAMETERS

### -ChangeFeedRetentionInDays
Menunjukkan durasi penyimpanan Umpan Perubahan dalam hari. Nilai minimum adalah 1 hari dan nilai maksimum adalah 146000 hari (400 tahun). Jangan pernah tentukan saat diaktifkan changeFeed akan mendapatkan nilai null dalam properti layanan, menunjukkan penyimpanan umpan perubahan yang tidak terbatas.

```yaml
Type: System.Int32
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
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultServiceVersion
Versi Layanan Default untuk Diatur

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

### -EnableChangeFeed
Aktifkan pembuatan log Ubah Umpan untuk akun penyimpanan dengan diatur ke $true, nonaktifkan Pembuatan log Ubah Umpan dengan mengatur ke $false.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsVersioningEnabled
Gets atau sets versioning is enabled if set to true.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: AccountName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Masukkan Id sumber Storage akun, atau Id Sumber Daya properti layanan Blob.

```yaml
Type: System.String
Parameter Sets: BlobServicePropertiesResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccount
Storage objek akun

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSStorageAccount
Parameter Sets: AccountObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageAccountName
Storage Akun.

```yaml
Type: System.String
Parameter Sets: AccountName
Aliases: AccountName, Name

Required: True
Position: 1
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSBlobServiceProperties

## CATATAN

## RELATED LINKS
