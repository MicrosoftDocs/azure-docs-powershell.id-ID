---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: EC6AB7E9-BC9F-4FA2-8172-144C9842D74C
online version: ''
schema: 2.0.0
ms.openlocfilehash: 6691110a97976a1cea5d7de5597e3d688aba4f44
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143043929"
---
# Get-AzureRemoteAppVmStaleAdObject

## SYNOPSIS
Mendapatkan objek di Azure Active Directory yang terkait dengan mesin virtual Azure RemoteApp yang tidak ada lagi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRemoteAppVmStaleAdObject -CollectionName <String> [-Credential <PSCredential>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRemoteAppVmStaleAdObject** mendapatkan objek di Azure Active Directory yang terkait dengan mesin virtual Azure RemoteApp yang tidak ada lagi.
Cmdlet ini menampilkan nama setiap objek yang didapatkannya.

## EXAMPLES

### Contoh 1: Mendapatkan objek basi untuk koleksi
```
PS C:\> Clear-AzureRemoteAppVmStaleAdObject -CollectionName "Contoso"
```

Perintah kedua ini mendapatkan objek basi untuk koleksi bernama Contoso.

## PARAMETERS

### -CollectionName
Menentukan nama koleksi Azure RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Kredensial
Menentukan kredensial yang memiliki hak untuk melakukan tindakan ini.
Untuk mendapatkan objek **PSCredential** , gunakan cmdlet **Get-Credential** .
Jika Anda tidak menentukan parameter ini, cmdlet ini menggunakan kredensial pengguna saat ini.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String

## NOTES

## RELATED LINKS

[Clear-AzureRemoteAppVmStaleAdObject](./Clear-AzureRemoteAppVmStaleAdObject.md)


