---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: A121B341-091D-42AD-B56A-3C75E25A1BF6
online version: ''
schema: 2.0.0
ms.openlocfilehash: b5da13ea6f41cca82cc4e87f6e92d575c23b9d8d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141922874"
---
# Add-AzureRemoteAppUser

## SYNOPSIS
Menambahkan pengguna ke koleksi Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureRemoteAppUser [-CollectionName] <String> [-Type] <PrincipalProviderType> [-UserUpn] <String[]>
 [-Alias <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRemoteAppUser** menambahkan pengguna ke koleksi Azure RemoteApp.

## EXAMPLES

### Contoh 1: Menambahkan pengguna menggunakan Akun Microsoft
```
PS C:\> Add-AzureRemoteAppUser -CollectionName "Contoso" -UserType MicrosoftAccount -UserUpn "PattiFuller@contoso.com"
```

Perintah ini menambahkan Akun PattiFuller@contoso.com Microsoft ke koleksi bernama Contoso.

### Contoh 2: Menambahkan pengguna menggunakan akun Azure Active Directory
```
PS C:\> Add-AzureRemoteAppUser -CollectionName "Contoso" -UserType OrgId -UserUpn "PattiFuller@contoso.com"
```

Perintah ini menambahkan akun PattiFuller@contoso.com Azure Active Directory ke koleksi bernama Contoso.

## PARAMETERS

### -Alias
Menentukan alias program yang diterbitkan.
Anda hanya dapat menggunakan parameter ini dalam mode penerbitan per aplikasi.

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

### -CollectionName
Menentukan nama koleksi Azure RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 1
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

### -Tipe
Menentukan tipe pengguna.
Nilai yang dapat diterima untuk parameter ini adalah: OrgId atau MicrosoftAccount.

```yaml
Type: PrincipalProviderType
Parameter Sets: (All)
Aliases: 
Accepted values: OrgId, MicrosoftAccount

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserUpn
Menentukan Nama Pokok Pengguna (UPN) pengguna, misalnya, PattiFuller@contoso.com.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRemoteAppUser](./Get-AzureRemoteAppUser.md)

[Hapus-AzureRemoteAppUser](./Remove-AzureRemoteAppUser.md)


