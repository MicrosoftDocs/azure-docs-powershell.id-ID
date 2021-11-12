---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: 3CFA6E31-E243-4B22-AE8F-1942DD324639
online version: https://docs.microsoft.com/en-us/powershell/module/azure.storage/new-azurestoragetablesastoken
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/New-AzureStorageTableSASToken.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/New-AzureStorageTableSASToken.md
ms.openlocfilehash: 76ed7737acb26cd713aa84b26a743f3e5e43874f
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132419713"
---
# New-AzureStorageTableSASToken

## SYNOPSIS
Menghasilkan token SAS untuk Azure Storage tabel.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SasPolicy
```
New-AzureStorageTableSASToken [-Name] <String> -Policy <String> [-Protocol <SharedAccessProtocol>]
 [-IPAddressOrRange <String>] [-StartTime <DateTime>] [-ExpiryTime <DateTime>] [-FullUri]
 [-StartPartitionKey <String>] [-StartRowKey <String>] [-EndPartitionKey <String>] [-EndRowKey <String>]
 [-Context <IStorageContext>] [<CommonParameters>]
```

### SasPermission
```
New-AzureStorageTableSASToken [-Name] <String> [-Permission <String>] [-Protocol <SharedAccessProtocol>]
 [-IPAddressOrRange <String>] [-StartTime <DateTime>] [-ExpiryTime <DateTime>] [-FullUri]
 [-StartPartitionKey <String>] [-StartRowKey <String>] [-EndPartitionKey <String>] [-EndRowKey <String>]
 [-Context <IStorageContext>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorageTableSASToken** menghasilkan token Shared Access Signature (SAS) untuk Azure Storage tabel.

## EXAMPLES

### Contoh 1: Buat token SAS yang memiliki izin penuh untuk tabel
```
C:\PS>New-AzureStorageTableSASToken -Name "ContosoResources" -Permission "raud"
```

Perintah ini menghasilkan token SAS dengan izin penuh untuk tabel bernama ContosoResources.
Token tersebut untuk izin membaca, menambahkan, memperbarui, dan menghapus.

### Contoh 2: Menghasilkan token SAS untuk rentang partisi
```
C:\PS>New-AzureStorageTableSASToken -Name "ContosoResources" -Permission "raud" -StartPartitionKey "a" -EndPartitionKey "b"
```

Perintah ini menghasilkan dan token SAS dengan izin penuh untuk tabel bernama ContosoResources.
The command limits the token to the range that the *StartPartitionKey* and *EndPartitionKey* specify.

### Contoh 3: Buat token SAS yang memiliki kebijakan akses tersimpan untuk tabel
```
C:\PS>New-AzureStorageTableSASToken -Name "ContosoResources" -Policy "ClientPolicy01"
```

Perintah ini menghasilkan token SAS untuk tabel bernama ContosoResources.
Perintah menentukan kebijakan akses tersimpan bernama ClientPolicy01.

## PARAMETERS

### -Konteks
Menentukan konteks penyimpanan Azure.
Untuk mendapatkan konteks penyimpanan, gunakan cmdlet New-AzureStorageContext.

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

### -EndPartitionKey
Menentukan kunci partisi dari akhir rentang untuk token yang dibuat cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: endpk

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndRowKey
Menentukan kunci baris untuk akhir rentang untuk token yang dibuat cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: endrk

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExpiryTime
Menentukan kapan token SAS kedaluwarsa.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullUri
Menunjukkan bahwa cmdlet ini mengembalikan URI antrean penuh dengan token SAS.

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

### -IPAddressOrRange
Menentukan alamat IP atau rentang alamat IP untuk menerima permintaan, seperti 168.1.5.65 atau 168.1.5.60-168.1.5.70.
Rentang bersifat inklusif.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama tabel Azure Storage.
Cmdlet ini membuat token SAS untuk tabel yang ditentukan parameter ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: N, Table

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Permission
Menentukan izin untuk Azure Storage tabel.

```yaml
Type: String
Parameter Sets: SasPermission
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kebijakan
Menentukan kebijakan akses tersimpan, yang mencakup izin untuk token SAS ini.

```yaml
Type: String
Parameter Sets: SasPolicy
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Menentukan protokol yang diizinkan untuk permintaan.
Nilai yang dapat diterima untuk parameter ini adalah:
* HttpsOnly
* HttpsOrhttp

Nilai defaultnya adalah HttpsOrHttp.

```yaml
Type: SharedAccessProtocol
Parameter Sets: (All)
Aliases: 
Accepted values: HttpsOnly, HttpsOrHttp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartPartitionKey
Menentukan kunci partisi dari awal rentang untuk token yang dibuat cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: startpk

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartRowKey
Menentukan kunci baris untuk awal rentang untuk token yang dibuat cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: startrk

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Menentukan kapan token SAS menjadi valid.

```yaml
Type: DateTime
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

### String

Parameter 'Name' menerima nilai tipe 'String' dari saluran

## OUTPUTS

### System.String

## CATATAN

## RELATED LINKS

[New-AzureStorageContext](./New-AzureStorageContext.md)
