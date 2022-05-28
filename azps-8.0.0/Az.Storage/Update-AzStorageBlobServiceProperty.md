---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/update-azstorageblobserviceproperty
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Update-AzStorageBlobServiceProperty.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Update-AzStorageBlobServiceProperty.md
ms.openlocfilehash: 811211e0cb70729fa59a2221128e15f6200ed18a
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145517638"
---
# Update-AzStorageBlobServiceProperty

## SYNOPSIS
Memodifikasi properti layanan untuk Azure Storage Blob service.

## SYNTAX

### AccountName (Default)
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
Cmdlet **Update-AzStorageBlobServiceProperty** memodifikasi properti layanan untuk Azure Storage Blob service.

## EXAMPLES

### Contoh 1: Atur Layanan Blob DefaultServiceVersion ke 2018-03-28
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

Perintah ini mengatur DefaultServiceVersion dari Blob Service ke 2018-03-28.

### Contoh 2: Aktifkan Changefeed pada layanan Blob akun Storage dengan ChangeFeedRetentionInDays sebagai 5 hari
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

Perintah ini memungkinkan Changefeed pada layanan Blob akun Storage dengan ChangeFeedRetentionInDays sebagai 5 hari.
Ubah dukungan umpan di Azure Blob Storage berfungsi dengan mendengarkan akun penyimpanan GPv2 atau Blob untuk setiap peristiwa pembuatan, modifikasi, atau penghapusan tingkat blob. Kemudian menghasilkan log peristiwa yang diurutkan untuk blob yang disimpan dalam kontainer $blobchangefeed dalam akun penyimpanan. Perubahan berseri dipertahankan sebagai file Apache Avro dan dapat diproses secara asinkron dan bertahap.
Jika tidak menentukan ChangeFeedRetentionInDays, akan mendapatkan nilai null di properti layanan, menunjukkan retensi tak terbatas dari umpan perubahan.

### Contoh 3: Aktifkan Penerapan Versi pada layanan Blob dari akun Storage
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

Perintah ini memungkinkan Penerapan Versi pada layanan Blob dari akun Storage

## PARAMETERS

### -ChangeFeedRetentionInDays
Menunjukkan durasi retensi changeFeed dalam hari. Nilai minimum adalah 1 hari dan nilai maksimum adalah 146000 hari (400 tahun). Jangan pernah menentukannya ketika changeFeed yang diaktifkan akan mendapatkan nilai null di properti layanan, menunjukkan retensi tak terbatas dari umpan perubahan.

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
Aktifkan pengelogan Umpan Perubahan untuk akun penyimpanan dengan diatur ke $true, nonaktifkan Pengelogan Umpan Perubahan dengan diatur ke $false.

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
Penerapan versi gets atau set diaktifkan jika diatur ke true.

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
Masukkan Id Sumber Daya akun Storage, atau Id Sumber Daya properti Blob service.

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
Storage Nama Akun.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSBlobServiceProperties

## NOTES

## RELATED LINKS
