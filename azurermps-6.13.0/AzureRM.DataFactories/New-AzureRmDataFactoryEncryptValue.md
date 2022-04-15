---
external help file: Microsoft.Azure.Commands.DataFactories.dll-Help.xml
Module Name: AzureRM.DataFactories
ms.assetid: 5BF24BC2-DEB6-4830-BDEA-841BAB070388
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.datafactories/new-azurermdatafactoryencryptvalue
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/DataFactories/Commands.DataFactories/help/New-AzureRmDataFactoryEncryptValue.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/DataFactories/Commands.DataFactories/help/New-AzureRmDataFactoryEncryptValue.md
ms.openlocfilehash: 5de4c34281b2122880a683f070e771dc15d93c5a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142388596"
---
# New-AzureRmDataFactoryEncryptValue

## SYNOPSIS
Mengenkripsi data sensitif.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByFactoryName (Default)
```
New-AzureRmDataFactoryEncryptValue [-DataFactoryName] <String> [[-Value] <SecureString>]
 [[-GatewayName] <String>] [[-Credential] <PSCredential>] [[-Type] <String>] [[-NonCredentialValue] <String>]
 [[-AuthenticationType] <String>] [[-Server] <String>] [[-Database] <String>] [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFactoryObject
```
New-AzureRmDataFactoryEncryptValue [-DataFactory] <PSDataFactory> [[-Value] <SecureString>]
 [[-GatewayName] <String>] [[-Credential] <PSCredential>] [[-Type] <String>] [[-NonCredentialValue] <String>]
 [[-AuthenticationType] <String>] [[-Server] <String>] [[-Database] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmDataFactoryEncryptValue** mengenkripsi data sensitif, seperti kata sandi atau string koneksi Microsoft SQL Server, dan mengembalikan nilai terenkripsi.

## EXAMPLES

### Contoh 1: Mengenkripsi string koneksi non-ODBC
```
PS C:\>$Value = ConvertTo-SecureString 'Data Source=ContosoServer;Initial Catalog=catelog;user id =user123;password=password123' -AsPlainText -Force 
PS C:\> New-AzureRmDataFactoryEncryptValue -GatewayName "WikiGateway" -DataFactoryName "WikiAdf" -Value $value -ResourceGroupName "ADF" -Type OnPremisesSqlLinkedService
```

Perintah pertama menggunakan cmdlet ConvertTo-SecureString untuk mengonversi string koneksi tertentu menjadi objek **SecureString** , lalu menyimpan objek tersebut dalam variabel $Value.
Untuk informasi selengkapnya, ketik .`Get-Help ConvertTo-SecureString`
Nilai yang diizinkan: SQL Server atau string koneksi Oracle.
Perintah kedua membuat nilai terenkripsi untuk objek yang disimpan di $Value untuk tipe pabrik data, gateway, grup sumber daya, dan layanan tertaut yang ditentukan.

### Contoh 2: Enkripsi string koneksi non-ODBC yang menggunakan autentikasi Windows.
```
PS C:\>$Value = ConvertTo-SecureString 'Data Source=ContosoServer;Initial Catalog=catelog;Integrated Security=True' -AsPlainText -Force
PS C:\> $Credential = Get-Credential
PS C:\> New-AzureRmDataFactoryEncryptValue -DataFactoryName "WikiADF" -GatewayName "WikiGateway" -ResourceGroupName "ADF" -Value $Value -Credential $Credential -Type OnPremisesSqlLinkedService $Value = ConvertTo-SecureString 'Data Source=ContosoServer;Initial Catalog=catelog;Integrated Security=True' -AsPlainText -Force
```

Perintah pertama menggunakan **ConvertTo-SecureString** untuk mengonversi string koneksi tertentu menjadi objek string aman, lalu menyimpan objek tersebut dalam variabel $Value.
Perintah kedua menggunakan cmdlet Get-Credential untuk mengumpulkan autentikasi windows (nama pengguna dan kata sandi), lalu menyimpan objek **PSCredential** tersebut dalam variabel $Credential.
Untuk informasi selengkapnya, ketik .`Get-Help Get-Credential`
Perintah ketiga membuat nilai terenkripsi untuk objek yang disimpan di $Value dan $Credential untuk pabrik data, gateway, grup sumber daya, dan tipe layanan tertaut yang ditentukan.

### Contoh 3: Mengenkripsi nama server dan kredensial untuk layanan tertaut sistem file
```
PS C:\>$Value = ConvertTo-SecureString '\\servername' -AsPlainText -Force
PS C:\> $Credential = Get-Credential
PS C:\> New-AzureRmDataFactoryEncryptValue -DataFactoryName "WikiADF" -GatewayName "WikiGateway" -ResourceGroupName "ADF" -Value $Value -Credential $Credential -Type OnPremisesFileSystemLinkedService
```

Perintah pertama menggunakan **ConvertTo-SecureString** untuk mengonversi string yang ditentukan menjadi string aman, lalu menyimpan objek tersebut dalam variabel $Value.
Perintah kedua menggunakan **Get-Credential** untuk mengumpulkan autentikasi windows (nama pengguna dan kata sandi), lalu menyimpan objek **PSCredential** tersebut dalam variabel $Credential.
Perintah ketiga membuat nilai terenkripsi untuk objek yang disimpan di $Value dan $Credential untuk pabrik data, gateway, grup sumber daya, dan tipe layanan tertaut yang ditentukan.

### Contoh 4: Mengenkripsi kredensial untuk layanan tertaut HDFS
```
PS C:\>$UserName = ConvertTo-SecureString "domain\\username" -AsPlainText -Force
$Password = ConvertTo-SecureString "password" -AsPlainText -Force
$Credential = New-Object System.Management.Automation.PSCredential ($UserName, $Password)
New-AzureRmDataFactoryEncryptValue -DataFactoryName "MyDataFactory" -ResourceGroupName "MyResourceGroup" -GatewayName "MyDataManagementGateway" -Type HdfsLinkedService -AuthenticationType Windows -Credential $Credential -NonCredentialValue "http://server01.com:50070/webhdfs/v1/user/username"
```

Perintah **ConvertTo-SecureString** mengonversi string tertentu menjadi string aman.
Perintah **Objek Baru** membuat objek PSCredential menggunakan string nama pengguna dan kata sandi yang aman.
Sebagai gantinya, Anda dapat menggunakan perintah **Get-Credential** untuk mengumpulkan autentikasi windows (nama pengguna dan kata sandi), lalu menyimpan objek **PSCredential yang** dikembalikan dalam variabel $credential seperti yang diperlihatkan dalam contoh sebelumnya.
Perintah **New-AzureRmDataFactoryEncryptValue** membuat nilai terenkripsi untuk objek yang disimpan di $Credential untuk tipe pabrik data, gateway, grup sumber daya, dan layanan tertaut yang ditentukan.

### Contoh 5: Mengenkripsi kredensial untuk layanan tertaut ODBC
```
PS C:\>$Content = ConvertTo-SecureString "UID=username@contoso;PWD=password;" -AsPlainText -Force
New-AzureRmDataFactoryEncryptValue -ResourceGroupName $RGName -DataFactoryName $DFName -GatewayName $Gateway -Type OnPremisesOdbcLinkedService -AuthenticationType Basic -NonCredentialValue "Driver={SQL Server};Server=server01.database.contoso.net; Database=HDISScenarioTest;" -Value $content
```

Perintah **ConvertTo-SecureString** mengonversi string tertentu menjadi string aman.
Perintah **New-AzureRmDataFactoryEncryptValue** membuat nilai terenkripsi untuk objek yang disimpan di $Value untuk tipe pabrik data, gateway, grup sumber daya, dan layanan tertaut yang ditentukan.

## PARAMETERS

### -AuthenticationType
Menentukan tipe autentikasi yang akan digunakan untuk menyambungkan ke sumber data.
Nilai yang dapat diterima untuk parameter ini adalah:
- Windows
- Dasar
- Anonim.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Windows, Basic, Anonymous

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kredensial
Menentukan kredensial autentikasi Windows (nama pengguna dan kata sandi) untuk digunakan.
Cmdlet ini mengenkripsi data kredensial yang Anda tentukan di sini.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Database
Menentukan nama database layanan yang ditautkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataFactory
Menentukan objek **PSDataFactory** .
Cmdlet ini mengenkripsi data untuk pabrik data yang ditentukan parameter ini.

```yaml
Type: Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory
Parameter Sets: ByFactoryObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DataFactoryName
Menentukan nama pabrik data.
Cmdlet ini mengenkripsi data untuk pabrik data yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: ByFactoryName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GatewayName
Menentukan nama gateway.
Cmdlet ini mengenkripsi data untuk gateway yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NonCredentialValue
Menentukan bagian non-kredensial dari string koneksi Konektivitas Database Terbuka (ODBC).
Parameter ini hanya berlaku untuk layanan tertaut ODBC.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya Azure.
Cmdlet ini mengenkripsi data untuk grup yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: ByFactoryName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Menentukan nama server layanan yang ditautkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tipe
Menentukan tipe layanan yang ditautkan.
Cmdlet ini mengenkripsi data untuk tipe layanan tertaut yang ditentukan parameter ini.
Nilai yang dapat diterima untuk parameter ini adalah:
- OnPremisesSqlLinkedService 
- OnPremisesFileSystemLinkedService 
- OnPremisesOracleLinkedService 
- OnPremisesOdbcLinkedService 
- OnPremisesPostgreSqlLinkedService 
- OnPremisesTeradataLinkedService 
- OnPremisesMySQLLinkedService 
- OnPremisesDB2LinkedService 
- OnPremisesSybaseLinkedService

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: OnPremisesSqlLinkedService, OnPremisesFileSystemLinkedService, OnPremisesOracleLinkedService, OnPremisesOdbcLinkedService, OnPremisesPostgreSqlLinkedService, OnPremisesTeradataLinkedService, OnPremisesMySQLLinkedService, OnPremisesDB2LinkedService, OnPremisesSybaseLinkedService, HdfsLinkedService

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value
Menentukan nilai untuk dienkripsi.
Untuk layanan lokal SQL Server tertaut dan layanan tertaut Oracle lokal, gunakan string koneksi.
Untuk layanan odbc lokal yang ditautkan, gunakan bagian kredensial string koneksi.
Untuk layanan tertaut sistem file lokal, jika sistem file lokal ke komputer gateway, gunakan Lokal atau localhost, dan jika sistem file berada di server yang berbeda dari komputer gateway, gunakan \\\\nama server.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

### System.String

## OUTPUTS

### System.String

## CATATAN
* Kata kunci: azure, azurerm, lengan, sumber daya, manajemen, manajer, data, pabrik

## RELATED LINKS

[New-AzureRmDataFactoryEncryptValue](./New-AzureRmDataFactoryEncryptValue.md)


