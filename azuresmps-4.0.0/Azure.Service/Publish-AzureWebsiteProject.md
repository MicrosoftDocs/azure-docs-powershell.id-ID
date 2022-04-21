---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: D866554F-78B0-4691-BA06-F625F9B0DFC8
online version: ''
schema: 2.0.0
ms.openlocfilehash: 4efef8226c247e0fb3da8fb701c80b65c8920eb4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142655524"
---
# Publish-AzureWebsiteProject

## SYNOPSIS
Menerbitkan proyek web Visual Studio ke situs web Microsoft Azure menggunakan WebDeploy.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ProjectFile
```
Publish-AzureWebsiteProject -ProjectFile <String> [-Configuration <String>] [-ConnectionString <Hashtable>]
 [-SkipAppData] [-DoNotDelete] [-Name <String>] [-Slot <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### Paket
```
Publish-AzureWebsiteProject -Package <String> [-ConnectionString <Hashtable>] [-Tokens <String>]
 [-SetParametersFile <String>] [-SkipAppData] [-DoNotDelete] [-Name <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Menerbitkan proyek web Visual Studio ke situs web Microsoft Azure menggunakan WebDeploy.
Ini bisa mengambil paket WebDeploy dan menerbitkan secara langsung, atau mengambil proyek web Visual Studio, menyusun proyek dan menerbitkan.
Ini juga bisa mengganti string koneksi di Web.config selama penerbitan.

## EXAMPLES

### Contoh 1
```
PS C:\> Publish-AzureWebsiteProject -Name site1 -ProjectFile .\WebApplication1.csproj -Configuration Debug
```

Buat proyek web Visual Studio dengan konfigurasi "Debug" (artinya gunakan Web.Debug.config) dan terbitkan ke Situs Web Microsoft Azure menggunakan WebDeploy.

### Contoh 2
```
PS C:\> Publish-AzureWebsiteProject -Name site1 -Package .\WebApplication1.zip
```

Menerbitkan file .zip Paket WebDeploy ke Situs Web Microsoft Azure menggunakan WebDeploy.

### Contoh 3
```
PS C:\> Publish-AzureWebsiteProject -Name site1 -Package .\WebApplication1
```

Menerbitkan folder Paket WebDeploy ke Situs Web Microsoft Azure menggunakan WebDeploy.

### Contoh 4
```
PS C:\> Publish-AzureWebsiteProject -Name site1 -ProjectFile .\WebApplication1.csproj -ConnectionString @{ DefaultConnection = "my connection string" }
```

Buat proyek web Visual Studio, timpa string koneksi "DefaultConnection" dalam Web.config dan terbitkan ke Situs Web Microsoft Azure menggunakan WebDeploy.

### Contoh 5
```
PS C:\> Publish-AzureWebsiteProject -Name site1 -ProjectFile .\WebApplication1.csproj -DefaultConnection "my connection string"
```

Buat proyek web Visual Studio, timpa string koneksi "DefaultConnection" dalam Web.config dan terbitkan ke Situs Web Microsoft Azure menggunakan WebDeploy.
Perhatikan bahwa -DefaultConnection adalah parameter dinamis yang ditambahkan dengan memilah Web.config.

## PARAMETERS

### -Configuration
Konfigurasi yang digunakan untuk menyusun proyek aplikasi web Visual Studio.

```yaml
Type: String
Parameter Sets: ProjectFile
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionString
String koneksi yang digunakan untuk penyebaran.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DoNotDelete
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

### -Nama
Nama situs web.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Paket
Folder paket WebDeploy untuk file zip proyek aplikasi web Visual Studio yang akan diterbitkan.

```yaml
Type: String
Parameter Sets: Package
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProjectFile
Proyek aplikasi web Visual Studio yang akan diterbitkan.

```yaml
Type: String
Parameter Sets: ProjectFile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SetParametersFile
```yaml
Type: String
Parameter Sets: Package
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipAppData
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

### -Slot
Nama slot situs web.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Token
```yaml
Type: String
Parameter Sets: Package
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Dapatkan-AzureWebsite](./Get-AzureWebsite.md)

[Baru-AzureSitus Web](./New-AzureWebsite.md)

[Hapus-AzureSitus Web](./Remove-AzureWebsite.md)

[Atur-AzureWebsite](./Set-AzureWebsite.md)


