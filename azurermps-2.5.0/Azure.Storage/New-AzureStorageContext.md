---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
Module Name: Azure.Storage
ms.assetid: 383402B2-6B7C-41AB-AFF9-36C86156B0A9
online version: https://docs.microsoft.com/en-us/powershell/module/azure.storage/new-azurestoragecontext
schema: 2.0.0
ms.openlocfilehash: 3a91c88fe80151ef8aa3934c484cfe9b6671a750
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143055215"
---
# New-AzureStorageContext

## SYNOPSIS
Membuat konteks Azure Storage.

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

### ConnectionString
```
New-AzureStorageContext -ConnectionString <String> [<CommonParameters>]
```

### LocalDevelopment
```
New-AzureStorageContext [-Local] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureStorageContext** membuat konteks Azure Storage.

## EXAMPLES

### Contoh 1: Membuat konteks dengan menentukan nama dan kunci akun penyimpanan
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >"
```

Perintah ini membuat konteks untuk akun bernama ContosoGeneral yang menggunakan kunci yang ditentukan.

### Contoh 2: Membuat konteks dengan menentukan string koneksi
```
C:\PS>New-AzureStorageContext -ConnectionString "DefaultEndpointsProtocol=https;AccountName=ContosoGeneral;AccountKey=< Storage Key for ContosoGeneral ends with == >;"
```

Perintah ini membuat konteks berdasarkan string koneksi yang ditentukan untuk akun ContosoGeneral.

### Contoh 3: Membuat konteks untuk akun penyimpanan anonim
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -Anonymous -Protocol "http"
```

Perintah ini membuat konteks untuk penggunaan anonim untuk akun bernama ContosoGeneral.
Perintah menentukan HTTP sebagai protokol koneksi.

### Contoh 4: Membuat konteks dengan menggunakan akun penyimpanan pengembangan lokal
```
C:\PS>New-AzureStorageContext -Local
```

Perintah ini membuat konteks dengan menggunakan akun penyimpanan pengembangan lokal.
Perintah menentukan parameter *Lokal* .

### Contoh 5: Mendapatkan kontainer untuk akun penyimpanan pengembang lokal
```
C:\PS>New-AzureStorageContext -Local | Get-AzureStorageContainer
```

Perintah ini membuat konteks dengan menggunakan akun penyimpanan pengembangan lokal, lalu meneruskan konteks baru ke cmdlet **Get-AzureStorageContainer** dengan menggunakan operator alur.
Perintah mendapatkan kontainer Azure Storage untuk akun penyimpanan pengembang lokal.

### Contoh 6: Mendapatkan beberapa kontainer
```
C:\PS>$Context01 = New-AzureStorageContext -Local 
PS C:\> $Context02 = New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >"
PS C:\> ($Context01, $Context02) | Get-AzureStorageContainer
```

Perintah pertama membuat konteks dengan menggunakan akun penyimpanan pengembangan lokal, lalu menyimpan konteks tersebut dalam variabel $Context 01.
Perintah kedua membuat konteks untuk akun bernama ContosoGeneral yang menggunakan kunci yang ditentukan, lalu menyimpan konteks tersebut dalam variabel $Context 02.
Perintah akhir mendapatkan kontainer untuk konteks yang disimpan di $Context 01 dan $Context 02 dengan menggunakan **Get-AzureStorageContainer**.

### Contoh 7: Membuat konteks dengan titik akhir
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >" -Endpoint "contosoaccount.core.windows.net"
```

Perintah ini membuat konteks Azure Storage yang memiliki titik akhir penyimpanan yang ditentukan.
Perintah membuat konteks untuk akun bernama ContosoGeneral yang menggunakan kunci yang ditentukan.

### Contoh 8: Membuat konteks dengan lingkungan tertentu
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >" -Environment "AzureChinaCloud"
```

Perintah ini membuat konteks penyimpanan Azure yang memiliki lingkungan Azure yang ditentukan.
Perintah membuat konteks untuk akun bernama ContosoGeneral yang menggunakan kunci yang ditentukan.

### Contoh 9: Membuat konteks dengan menggunakan token SAS
```
C:\PS>$SasToken = New-AzureStorageContainerSASToken -Name "ContosoMain" -Permission "rad"
PS C:\> $Context = New-AzureStorageContext -StorageAccountName "ContosoGeneral" -SasToken $SasToken
PS C:\> $Context | Get-AzureStorageBlob -Container "ContosoMain"
```

Perintah pertama menghasilkan token SAS dengan menggunakan cmdlet **New-AzureStorageContainerSASToken** untuk kontainer bernama ContosoMain, lalu menyimpan token tersebut dalam variabel $SasToken.
Token tersebut untuk izin baca, tambahkan, perbarui, dan hapus.
Perintah kedua membuat konteks untuk akun bernama ContosoGeneral yang menggunakan token SAS yang disimpan dalam $SasToken, lalu menyimpan konteks tersebut dalam variabel $Context.
Perintah akhir mencantumkan semua blob yang terkait dengan kontainer bernama ContosoMain dengan menggunakan konteks yang disimpan dalam $Context.

## PARAMETERS

### -Anonim
Menunjukkan bahwa cmdlet ini membuat konteks Azure Storage untuk masuk anonim.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AnonymousAccount, AnonymousAccountEnvironment
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionString
Menentukan string koneksi untuk konteks Azure Storage.

```yaml
Type: System.String
Parameter Sets: ConnectionString
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Titik akhir
Menentukan titik akhir untuk konteks Azure Storage.

```yaml
Type: System.String
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
Untuk informasi selengkapnya, ketik `Get-Help Get-AzureEnvironment`.

```yaml
Type: System.String
Parameter Sets: AccountNameAndKeyEnvironment, AnonymousAccountEnvironment
Aliases: Name, EnvironmentName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: SasTokenWithAzureEnvironment
Aliases: Name, EnvironmentName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokal
Menunjukkan bahwa cmdlet ini membuat konteks dengan menggunakan akun penyimpanan pengembangan lokal.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LocalDevelopment
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protokol
Protokol Transfer (https/http).

```yaml
Type: System.String
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
Menentukan token Tanda Tangan Akses Bersama (SAS) untuk konteksnya.

```yaml
Type: System.String
Parameter Sets: SasToken, SasTokenWithAzureEnvironment
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountKey
Menentukan kunci akun Azure Storage.
Cmdlet ini membuat konteks untuk kunci yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: AccountNameAndKey, AccountNameAndKeyEnvironment
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountName
Menentukan nama akun Azure Storage.
Cmdlet ini membuat konteks untuk akun yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: AccountNameAndKey, AccountNameAndKeyEnvironment, AnonymousAccount, AnonymousAccountEnvironment, SasToken, SasTokenWithAzureEnvironment
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.WindowsAzure.Commands. Storage. AzureStorageContext

## NOTES

## RELATED LINKS

[Get-AzureStorageBlob](./Get-AzureStorageBlob.md)

[New-AzureStorageContainerSASToken](./New-AzureStorageContainerSASToken.md)


