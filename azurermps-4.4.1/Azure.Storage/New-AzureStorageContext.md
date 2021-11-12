---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
ms.assetid: 383402B2-6B7C-41AB-AFF9-36C86156B0A9
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/New-AzureStorageContext.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/New-AzureStorageContext.md
ms.openlocfilehash: b705f5b81fc592670151f9cf5fcf1d7caf8636ba
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422380"
---
# New-AzureStorageContext

## SYNOPSIS
Membuat Azure Storage konteks.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### AccountNameAndKey (Default)
```
New-AzureStorageContext [-StorageAccountName] <String> [-StorageAccountKey] <String> [-Protocol <String>]
 [-Endpoint <String>] [<CommonParameters>]
```

### AccountNameAndKeyEnvironment
```
New-AzureStorageContext [-StorageAccountName] <String> [-StorageAccountKey] <String> [-Protocol <String>]
 -Environment <String> [<CommonParameters>]
```

### AnonymousAccount
```
New-AzureStorageContext [-StorageAccountName] <String> [-Anonymous] [-Protocol <String>] [-Endpoint <String>]
 [<CommonParameters>]
```

### AnonymousAccountEnvironment
```
New-AzureStorageContext [-StorageAccountName] <String> [-Anonymous] [-Protocol <String>] -Environment <String>
 [<CommonParameters>]
```

### SasToken
```
New-AzureStorageContext [-StorageAccountName] <String> -SasToken <String> [-Protocol <String>]
 [-Endpoint <String>] [<CommonParameters>]
```

### SasTokenWithAzureEnvironment
```
New-AzureStorageContext [-StorageAccountName] <String> -SasToken <String> -Environment <String>
 [<CommonParameters>]
```

### String Koneksi
```
New-AzureStorageContext -ConnectionString <String> [<CommonParameters>]
```

### LocalDevelopment
```
New-AzureStorageContext [-Local] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorageContext** membuat Azure Storage konteks.

## EXAMPLES

### Contoh 1: Buat konteks dengan menentukan nama dan kunci akun penyimpanan
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >"
```

Perintah ini akan membuat konteks untuk akun bernama ContosoGeneral yang menggunakan kunci tertentu.

### Contoh 2: Membuat konteks dengan menentukan string koneksi
```
C:\PS>New-AzureStorageContext -ConnectionString "DefaultEndpointsProtocol=https;AccountName=ContosoGeneral;AccountKey=< Storage Key for ContosoGeneral ends with == >;"
```

Perintah ini akan membuat konteks berdasarkan string koneksi yang ditentukan untuk akun ContosoGeneral.

### Contoh 3: Buat konteks untuk akun penyimpanan anonim
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -Anonymous -Protocol "http"
```

Perintah ini akan membuat konteks untuk penggunaan anonim bagi akun bernama ContosoGeneral.
Perintah menentukan HTTP sebagai protokol koneksi.

### Contoh 4: Buat konteks menggunakan akun penyimpanan pengembangan lokal
```
C:\PS>New-AzureStorageContext -Local
```

Perintah ini akan membuat konteks menggunakan akun penyimpanan pengembangan lokal.
Perintah menentukan *Parameter* lokal.

### Contoh 5: Dapatkan wadah untuk akun penyimpanan pengembang lokal
```
C:\PS>New-AzureStorageContext -Local | Get-AzureStorageContainer
```

Perintah ini membuat konteks dengan menggunakan akun penyimpanan pengembangan lokal, lalu meneruskan konteks baru ke cmdlet **Get-AzureStorageContainer** menggunakan operator pipeline.
Perintah tersebut mendapatkan Azure Storage khusus untuk akun penyimpanan pengembang lokal.

### Contoh 6: Dapatkan beberapa wadah
```
C:\PS>$Context01 = New-AzureStorageContext -Local 
PS C:\> $Context02 = New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >"
PS C:\> ($Context01, $Context02) | Get-AzureStorageContainer
```

Perintah pertama membuat konteks dengan menggunakan akun penyimpanan pengembangan lokal, lalu menyimpan konteks tersebut dalam variabel $Context 01.

Perintah kedua membuat konteks untuk akun bernama ContosoGeneral yang menggunakan kunci yang ditentukan, lalu menyimpan konteks tersebut dalam variabel $Context 02.

Perintah terakhir mendapatkan wadah untuk konteks yang disimpan di $Context 01 dan $Context 02 dengan menggunakan **Get-AzureStorageContainer**.

### Contoh 7: Membuat konteks dengan titik akhir
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >" -Endpoint "contosoaccount.core.windows.net"
```

Perintah ini akan membuat Azure Storage yang memiliki titik akhir penyimpanan yang ditentukan.
Perintah membuat konteks untuk akun bernama ContosoGeneral yang menggunakan kunci yang ditentukan.

### Contoh 8: Membuat konteks dengan lingkungan tertentu
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >" -Environment "AzureChinaCloud"
```

Perintah ini akan membuat konteks penyimpanan Azure yang memiliki lingkungan Azure tertentu.
Perintah membuat konteks untuk akun bernama ContosoGeneral yang menggunakan kunci yang ditentukan.

### Contoh 9: Membuat konteks dengan menggunakan token SAS
```
C:\PS>$SasToken = New-AzureStorageContainerSASToken -Name "ContosoMain" -Permission "raud"
PS C:\> $Context = New-AzureStorageContext -StorageAccountName "ContosoGeneral" -SasToken $SasToken
PS C:\> $Context | Get-AzureStorageBlob -Container "ContosoMain"
```

Perintah pertama menghasilkan token SAS menggunakan cmdlet **New-AzureStorageContainerSASToken** untuk wadah bernama ContosoMain, lalu menyimpan token tersebut di $SasToken pelanggan.
Token tersebut untuk izin membaca, menambahkan, memperbarui, dan menghapus.

Perintah kedua membuat konteks untuk akun bernama ContosoGeneral yang menggunakan token SAS yang disimpan di $SasToken, lalu menyimpan konteks tersebut di variabel $Context mereka.

Perintah akhir mencantumkan semua blob yang terkait dengan wadah bernama ContosoMain dengan menggunakan konteks yang disimpan di $Context.

## PARAMETERS

### -Anonymous
Mengindikasikan bahwa cmdlet ini membuat konteks Azure Storage untuk masuk anonim.

```yaml
Type: SwitchParameter
Parameter Sets: AnonymousAccount, AnonymousAccountEnvironment
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionString
Menentukan string koneksi untuk Azure Storage konteks.

```yaml
Type: String
Parameter Sets: ConnectionString
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Titik akhir
Menentukan titik akhir untuk Azure Storage konteks.

```yaml
Type: String
Parameter Sets: AccountNameAndKey, AnonymousAccount, SasToken
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkungan
Menentukan lingkungan Azure.
Nilai yang dapat diterima untuk parameter ini adalah: AzureCloud dan AzureChinaCloud.
Untuk informasi selengkapnya, ketik `Get-Help Get-AzureEnvironment` .

```yaml
Type: String
Parameter Sets: AccountNameAndKeyEnvironment, AnonymousAccountEnvironment
Aliases: Name, EnvironmentName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: SasTokenWithAzureEnvironment
Aliases: Name, EnvironmentName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokal
Mengindikasikan bahwa cmdlet ini membuat konteks dengan menggunakan akun penyimpanan pengembangan lokal.

```yaml
Type: SwitchParameter
Parameter Sets: LocalDevelopment
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Protokol Transfer (https/http).

```yaml
Type: String
Parameter Sets: AccountNameAndKey, AccountNameAndKeyEnvironment, AnonymousAccount, AnonymousAccountEnvironment, SasToken
Aliases: 
Accepted values: Http, Https

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SasToken
Menentukan token Shared Access Signature (SAS) untuk konteksnya.

```yaml
Type: String
Parameter Sets: SasToken, SasTokenWithAzureEnvironment
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountKey
Menentukan Azure Storage akun.
Cmdlet ini akan membuat konteks untuk kunci yang ditentukan parameter ini.

```yaml
Type: String
Parameter Sets: AccountNameAndKey, AccountNameAndKeyEnvironment
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountName
Menentukan nama Azure Storage akun.
Cmdlet ini membuat konteks untuk akun yang ditentukan parameter ini.

```yaml
Type: String
Parameter Sets: AccountNameAndKey, AccountNameAndKeyEnvironment, AnonymousAccount, AnonymousAccountEnvironment, SasToken, SasTokenWithAzureEnvironment
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### AzureStorageContext

## CATATAN

## RELATED LINKS

[Get-AzureStorageBlob](./Get-AzureStorageBlob.md)

[New-AzureStorageContainerSASToken](./New-AzureStorageContainerSASToken.md)


