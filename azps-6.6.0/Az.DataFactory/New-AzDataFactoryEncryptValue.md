---
external help file: Microsoft.Azure.PowerShell.Cmdlets.DataFactories.dll-Help.xml
Module Name: Az.DataFactory
ms.assetid: 5BF24BC2-DEB6-4830-BDEA-841BAB070388
online version: https://docs.microsoft.com/powershell/module/az.datafactory/new-azdatafactoryencryptvalue
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/New-AzDataFactoryEncryptValue.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataFactory/DataFactoryV2/help/New-AzDataFactoryEncryptValue.md
ms.openlocfilehash: 2628721aceb9d4176c3cc43e58dcc517c7a7ff07
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136383174"
---
# New-AzDataFactoryEncryptValue

## SYNOPSIS
Mengenkripsi data sensitif.

## SYNTAX

### ByFactoryName (Default)
```
New-AzDataFactoryEncryptValue [-DataFactoryName] <String> [[-Value] <SecureString>] [-GatewayName] <String>
 [[-Credential] <PSCredential>] [[-Type] <String>] [[-NonCredentialValue] <String>]
 [[-AuthenticationType] <String>] [[-Server] <String>] [[-Database] <String>] [-ResourceGroupName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFactoryObject
```
New-AzDataFactoryEncryptValue [-DataFactory] <PSDataFactory> [[-Value] <SecureString>] [-GatewayName] <String>
 [[-Credential] <PSCredential>] [[-Type] <String>] [[-NonCredentialValue] <String>]
 [[-AuthenticationType] <String>] [[-Server] <String>] [[-Database] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzDataFactoryEncryptValue** mengenkripsi data sensitif, seperti kata sandi atau string koneksi Microsoft SQL Server, dan mengembalikan nilai terenkripsi.

## EXAMPLES

### Contoh 1: Mengenkripsi string koneksi non-ODBC
```
PS C:\>$Value = ConvertTo-SecureString 'Data Source=ContosoServer;Initial Catalog=catalog;user id =user123;password=password123' -AsPlainText -Force 
PS C:\> New-AzDataFactoryEncryptValue -GatewayName "WikiGateway" -DataFactoryName "WikiAdf" -Value $value -ResourceGroupName "ADF" -Type OnPremisesSqlLinkedService
```

Perintah pertama menggunakan cmdlet ConvertTo-SecureString untuk mengonversi string koneksi yang ditentukan menjadi objek **SecureString,** lalu menyimpan objek tersebut dalam $Value variabel.
Untuk informasi selengkapnya, ketik `Get-Help ConvertTo-SecureString` .
Nilai yang diperbolehkan: SQL Server atau string koneksi Oracle.
Perintah kedua membuat nilai terenkripsi untuk objek yang disimpan di $Value pabrik data, gateway, grup sumber daya, dan tipe layanan yang ditautkan yang ditentukan.

### Contoh 2: Mengenkripsi string koneksi non-ODBC yang menggunakan Windows autentikasi.
```
PS C:\>$Value = ConvertTo-SecureString 'Data Source=ContosoServer;Initial Catalog=catalog;Integrated Security=True' -AsPlainText -Force
PS C:\> $Credential = Get-Credential
PS C:\> New-AzDataFactoryEncryptValue -DataFactoryName "WikiADF" -GatewayName "WikiGateway" -ResourceGroupName "ADF" -Value $Value -Credential $Credential -Type OnPremisesSqlLinkedService $Value = ConvertTo-SecureString 'Data Source=ContosoServer;Initial Catalog=catalog;Integrated Security=True' -AsPlainText -Force
```

Perintah pertama menggunakan **ConvertTo-SecureString** untuk mengonversi string koneksi yang ditentukan menjadi objek string aman, lalu menyimpan objek tersebut dalam $Value variabel.
Perintah kedua menggunakan cmdlet Get-Credential untuk mengumpulkan autentikasi windows (nama pengguna dan kata sandi), lalu menyimpan objek **PSCredential** tersebut di $Credential variabel.
Untuk informasi selengkapnya, ketik `Get-Help Get-Credential` .
Perintah ketiga membuat nilai terenkripsi untuk objek yang disimpan di $Value dan $Credential untuk pabrik data, gateway, grup sumber daya, dan tipe layanan yang ditautkan.

### Contoh 3: Enkripsi nama server dan kredensial untuk Layanan tertaut sistem file
```
PS C:\>$Value = ConvertTo-SecureString '\\servername' -AsPlainText -Force
PS C:\> $Credential = Get-Credential
PS C:\> New-AzDataFactoryEncryptValue -DataFactoryName "WikiADF" -GatewayName "WikiGateway" -ResourceGroupName "ADF" -Value $Value -Credential $Credential -Type OnPremisesFileSystemLinkedService
```

Perintah pertama menggunakan **ConvertTo-SecureString** untuk mengonversi string yang ditentukan menjadi string aman, lalu menyimpan objek tersebut dalam $Value variabel.
Perintah kedua menggunakan **Get-Credential** untuk mengumpulkan Windows autentikasi (nama pengguna dan kata sandi), lalu menyimpan objek **PSCredential** tersebut di $Credential kedua.
Perintah ketiga membuat nilai terenkripsi untuk objek yang disimpan di $Value dan $Credential untuk pabrik data, gateway, grup sumber daya, dan tipe layanan yang ditautkan.

### Contoh 4: Mengenkripsi kredensial untuk layanan tertaut HDFS
```
PS C:\>$UserName = ConvertTo-SecureString "domain\\username" -AsPlainText -Force
$Password = ConvertTo-SecureString "password" -AsPlainText -Force
$Credential = New-Object System.Management.Automation.PSCredential ($UserName, $Password)
New-AzDataFactoryEncryptValue -DataFactoryName "MyDataFactory" -ResourceGroupName "MyResourceGroup" -GatewayName "MyDataManagementGateway" -Type HdfsLinkedService -AuthenticationType Windows -Credential $Credential -NonCredentialValue "http://server01.com:50070/webhdfs/v1/user/username"
```

Perintah **ConvertTo-SecureString** mengonversi string yang ditentukan menjadi string aman.
Perintah **Objek Baru** membuat objek PSCredential menggunakan nama pengguna dan string kata sandi yang aman.
Sebaliknya, Anda bisa menggunakan perintah **Get-Credential** untuk mengumpulkan autentikasi Windows (nama pengguna dan kata sandi), lalu menyimpan objek **PSCredential** yang dikembalikan dalam variabel $credential seperti yang diperlihatkan di contoh sebelumnya.
Perintah **New-AzDataFactoryEncryptValue** membuat nilai terenkripsi untuk objek yang disimpan di $Credential untuk pabrik data, gateway, grup sumber daya, dan tipe layanan yang ditautkan.

### Contoh 5: Mengenkripsi kredensial untuk layanan tertaut ODBC
```
PS C:\>$Content = ConvertTo-SecureString "UID=username@contoso;PWD=password;" -AsPlainText -Force
New-AzDataFactoryEncryptValue -ResourceGroupName $RGName -DataFactoryName $DFName -GatewayName $Gateway -Type OnPremisesOdbcLinkedService -AuthenticationType Basic -NonCredentialValue "Driver={SQL Server};Server=server01.database.contoso.net; Database=HDISScenarioTest;" -Value $content
```

Perintah **ConvertTo-SecureString** mengonversi string yang ditentukan menjadi string aman.
Perintah **New-AzDataFactoryEncryptValue** membuat nilai terenkripsi untuk objek yang disimpan di $Value untuk pabrik data, gateway, grup sumber daya, dan tipe layanan yang ditautkan.

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

### -Credential
Menentukan lokasi Windows autentikasi (nama pengguna dan kata sandi) yang akan digunakan.
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
Menentukan nama database dari layanan yang ditautkan.

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
Menentukan objek **PSDataFactory.**
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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -GatewayName
Menentukan nama gateway.
Cmdlet ini mengenkripsi data untuk gateway yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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
Menentukan nama server dari layanan yang ditautkan.

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
Cmdlet ini mengenkripsi data untuk tipe layanan yang ditautkan yang ditentukan parameter ini.
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
Untuk layanan terkait SQL Server tertaut dan layanan oracle lokal yang ditautkan, gunakan string koneksi.
Untuk layanan tertaut ODBC di tempat, gunakan bagian kredensial dari string koneksi.
Untuk layanan tertaut sistem file lokal, jika sistem file ber lokal untuk komputer gateway, gunakan Local atau localhost, dan jika sistem file berada di server berbeda dari komputer gateway, gunakan \\ \\ nama server.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.DataFactories.Models.PSDataFactory

### System.String

## OUTPUTS

### System.String

## CATATAN
* Kata kunci: azure, azurerm, arm, resource, management, manager, data, factories

## RELATED LINKS

[New-AzDataFactoryEncryptValue](./New-AzDataFactoryEncryptValue.md)


