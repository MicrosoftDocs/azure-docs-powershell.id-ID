---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: A6B274EA-7FF2-46B0-8622-0DD17E9ADDD6
online version: ''
schema: 2.0.0
ms.openlocfilehash: 2aff61aa61f9f1d44efa17f5c756e8cdd3ae5a14
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142095031"
---
# Get-AzureRemoteAppSession

## SYNOPSIS
Mencantumkan semua sesi Azure RemoteApp yang aktif dan terputus untuk koleksi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRemoteAppSession [-CollectionName] <String> [[-UserUpn] <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRemoteAppSession** mencantumkan semua sesi Azure RemoteApp yang aktif dan terputus untuk koleksi Azure RemoteApp.

## EXAMPLES

### Contoh 1: Mencantumkan semua sesi dalam koleksi
```
PS C:\> Get-AzureRemoteAppSession -CollectionName "ContosoApps"
```

Perintah ini mencantumkan semua sesi dalam koleksi Azure RemoteApp bernama ContosoApps.

## PARAMETERS

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

### -UserUpn
Menentukan Nama Pokok Pengguna (UPN) pengguna untuk mendapatkan sesi Azure RemoteApp.
Misalnya, UPN bisa dalam format berikut: PattiFuller@contoso.com.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Putuskan sambungan-AzureRemoteAppSession](./Disconnect-AzureRemoteAppSession.md)

[Invoke-AzureRemoteAppSessionLogoff](./Invoke-AzureRemoteAppSessionLogoff.md)

[Kirim-AzureRemoteAppSessionMessage](./Send-AzureRemoteAppSessionMessage.md)


