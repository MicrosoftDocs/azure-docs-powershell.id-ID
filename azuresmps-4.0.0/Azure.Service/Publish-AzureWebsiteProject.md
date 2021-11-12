---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: D866554F-78B0-4691-BA06-F625F9B0DFC8
online version: ''
schema: 2.0.0
ms.openlocfilehash: 984d5dcace1e0f0424706ce83173250d76e39077cb11c3d536aee41480f9dd64
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417723"
---
# Publish-AzureWebsiteProject

## SYNOPSIS
Menerbitkan proyek Visual Studio web ke situs web Microsoft Azure menggunakan WebDeploy.

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
Menerbitkan proyek Visual Studio web ke situs web Microsoft Azure menggunakan WebDeploy.
Program dapat mengambil paket WebDeploy dan menerbitkan secara langsung, atau mengambil Visual Studio web proyek, menyusun proyek, dan menerbitkannya.
Ini juga bisa mengganti string koneksi dalam Web.config penerbitan.

## EXAMPLES

### Contoh 1
```
PS C:\> Publish-AzureWebsiteProject -Name site1 -ProjectFile .\WebApplication1.csproj -Configuration Debug
```

Buat proyek web Visual Studio dengan konfigurasi "Debug" (berarti gunakan Web.Debug.config) dan terbitkan ke Situs Web Microsoft Azure menggunakan WebDeploy.

### Contoh 2
```
PS C:\> Publish-AzureWebsiteProject -Name site1 -Package .\WebApplication1.zip
```

Menerbitkan file WebDeploy Package .zip ke situs Microsoft Azure Web menggunakan WebDeploy.

### Contoh 3
```
PS C:\> Publish-AzureWebsiteProject -Name site1 -Package .\WebApplication1
```

Menerbitkan folder Paket WebDeploy ke situs web Microsoft Azure menggunakan WebDeploy.

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
Perhatikan bahwa -DefaultConnection adalah parameter dinamis yang ditambahkan dengan melakukan penguraian Web.config.

## PARAMETERS

### -Configuration
Konfigurasi yang digunakan untuk menyusun Visual Studio aplikasi web.

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
String koneksi yang digunakan untuk penggunaan.

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
Folder paket WebDeploy untuk file zip Visual Studio proyek aplikasi web yang akan diterbitkan.

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
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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
Proyek Visual Studio web yang akan diterbitkan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureWebsite](./Get-AzureWebsite.md)

[New-AzureWebsite](./New-AzureWebsite.md)

[Remove-AzureWebsite](./Remove-AzureWebsite.md)

[Set-AzureWebsite](./Set-AzureWebsite.md)


