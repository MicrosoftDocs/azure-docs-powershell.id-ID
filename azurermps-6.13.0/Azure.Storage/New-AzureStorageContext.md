---
external help file: Microsoft.WindowsAzure.Commands.Storage.dll-Help.xml
Module Name: Azure.Storage
ms.assetid: 383402B2-6B7C-41AB-AFF9-36C86156B0A9
online version: https://docs.microsoft.com/en-us/powershell/module/azure.storage/new-azurestoragecontext
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/New-AzureStorageContext.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/Storage/Commands.Storage/help/New-AzureStorageContext.md
ms.openlocfilehash: 9de6b2b52205bdf80de9c57e3e338f4b7216c5ee
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141888470"
---
# New-AzureStorageContext

## SYNOPSIS
Membuat konteks Azure Storage.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### OAuthAccount (Default)
```
New-AzureStorageContext [-StorageAccountName] <String> [-UseConnectedAccount] [-Protocol <String>]
 [-Endpoint <String>] [<CommonParameters>]
```

### AccountNameAndKey
```
New-AzureStorageContext [-StorageAccountName] <String> [-StorageAccountKey] <String> [-Protocol <String>]
 [-Endpoint <String>] [<CommonParameters>]
```

### AccountNameAndKeyEnvironment
```
New-AzureStorageContext [-StorageAccountName] <String> [-StorageAccountKey] <String> [-Protocol <String>]
 -Environment <String> [<CommonParameters>]
```

### AnonimAccount
```
New-AzureStorageContext [-StorageAccountName] <String> [-Anonymous] [-Protocol <String>] [-Endpoint <String>]
 [<CommonParameters>]
```

### AnonimAccountEnvironment
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

### OAuthAccountEnvironment
```
New-AzureStorageContext [-StorageAccountName] <String> [-UseConnectedAccount] [-Protocol <String>]
 -Environment <String> [<CommonParameters>]
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

### Contoh 4: Membuat konteks menggunakan akun penyimpanan pengembangan lokal
```
C:\PS>New-AzureStorageContext -Local
```

Perintah ini membuat konteks dengan menggunakan akun penyimpanan pengembangan lokal.
Perintah menentukan parameter *Lokal* .

### Contoh 5: Dapatkan wadah untuk akun penyimpanan pengembang lokal
```
C:\PS>New-AzureStorageContext -Local | Get-AzureStorageContainer
```

Perintah ini membuat konteks dengan menggunakan akun penyimpanan pengembangan lokal, lalu meneruskan konteks baru ke cmdlet **Get-AzureStorageContainer** menggunakan operator pipeline.
Perintah mendapatkan wadah Azure Storage untuk akun penyimpanan pengembang lokal.

### Contoh 6: Dapatkan beberapa wadah
```
C:\PS>$Context01 = New-AzureStorageContext -Local 
PS C:\> $Context02 = New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >"
PS C:\> ($Context01, $Context02) | Get-AzureStorageContainer
```

Perintah pertama membuat konteks dengan menggunakan akun penyimpanan pengembangan lokal, lalu menyimpan konteks tersebut dalam variabel $Context 01.
Perintah kedua membuat konteks untuk akun bernama ContosoGeneral yang menggunakan kunci yang ditentukan, lalu menyimpan konteks tersebut dalam variabel $Context 02.
Perintah akhir mendapatkan wadah untuk konteks yang disimpan di $Context 01 dan $Context 02 dengan menggunakan **Get-AzureStorageContainer**.

### Contoh 7: Membuat konteks dengan titik akhir
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >" -Endpoint "contosoaccount.core.windows.net"
```

Perintah ini membuat konteks Azure Storage yang memiliki titik akhir penyimpanan tertentu.
Perintah membuat konteks untuk akun bernama ContosoGeneral yang menggunakan kunci yang ditentukan.

### Contoh 8: Membuat konteks dengan lingkungan tertentu
```
C:\PS>New-AzureStorageContext -StorageAccountName "ContosoGeneral" -StorageAccountKey "< Storage Key for ContosoGeneral ends with == >" -Environment "AzureChinaCloud"
```

Perintah ini membuat konteks penyimpanan Azure yang memiliki lingkungan Azure yang ditentukan.
Perintah membuat konteks untuk akun bernama ContosoGeneral yang menggunakan kunci yang ditentukan.

### Contoh 9: Membuat konteks menggunakan token SAS
```
C:\PS>$SasToken = New-AzureStorageContainerSASToken -Name "ContosoMain" -Permission "rad"
PS C:\> $Context = New-AzureStorageContext -StorageAccountName "ContosoGeneral" -SasToken $SasToken
PS C:\> $Context | Get-AzureStorageBlob -Container "ContosoMain"
```

Perintah pertama menghasilkan token SAS menggunakan cmdlet **New-AzureStorageContainerSASToken** untuk wadah bernama ContosoMain, lalu menyimpan token tersebut dalam variabel $SasToken.
Token tersebut adalah untuk izin baca, tambahkan, perbarui, dan hapus.
Perintah kedua membuat konteks untuk akun bernama ContosoGeneral yang menggunakan token SAS yang disimpan di $SasToken, lalu menyimpan konteks tersebut dalam variabel $Context.
Perintah akhir mencantumkan semua blob yang terkait dengan wadah bernama ContosoMain menggunakan konteks yang disimpan di $Context.

### Contoh 10: Membuat konteks menggunakan Autentikasi OAuth
```
C:\PS>Connect-AzureRmAccount
C:\PS> $Context = New-AzureStorageContext -StorageAccountName "myaccountname" -UseConnectedAccount
```

Perintah ini membuat konteks menggunakan OAuth Authentication.

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
Parameter Sets: OAuthAccount, AccountNameAndKey, AnonymousAccount, SasToken
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
Untuk informasi selengkapnya, ketik .`Get-Help Get-AzureEnvironment`

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
Parameter Sets: SasTokenWithAzureEnvironment, OAuthAccountEnvironment
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
Parameter Sets: OAuthAccount, AccountNameAndKey, AccountNameAndKeyEnvironment, AnonymousAccount, AnonymousAccountEnvironment, SasToken, OAuthAccountEnvironment
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
Parameter Sets: OAuthAccount, AccountNameAndKey, AccountNameAndKeyEnvironment, AnonymousAccount, AnonymousAccountEnvironment, SasToken, SasTokenWithAzureEnvironment, OAuthAccountEnvironment
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseConnectedAccount
Menunjukkan bahwa cmdlet ini membuat konteks Azure Storage dengan OAuth Authentication.
Cmdlet akan menggunakan OAuth Authentication secara default, ketika anthentication lain tidak ditentukan.

```yaml
Type: SwitchParameter
Parameter Sets: OAuthAccount, OAuthAccountEnvironment
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseConnectedAccount
Menunjukkan bahwa cmdlet ini membuat konteks Azure Storage dengan OAuth Authentication.
Cmdlet akan menggunakan OAuth Authentication secara default, ketika anthentication lain tidak ditentukan.

```yaml
Type: SwitchParameter
Parameter Sets: OAuthAccount, OAuthAccountEnvironment
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.WindowsAzure.Commands. Storage. AzureStorageContext

## CATATAN

## RELATED LINKS

[Get-AzureStorageBlob](./Get-AzureStorageBlob.md)

[AzureStorageContainerSASToken baru](./New-AzureStorageContainerSASToken.md)


