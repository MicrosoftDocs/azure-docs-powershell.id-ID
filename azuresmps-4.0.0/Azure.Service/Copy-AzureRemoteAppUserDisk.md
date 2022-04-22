---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-help.xml
ms.assetid: 02F429EA-FE9A-427F-86B5-C9C4275FD3EA
online version: ''
schema: 2.0.0
ms.openlocfilehash: d4b326bc556c32559ce1a2545c5b50f8a6db7443
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143044271"
---
# Copy-AzureRemoteAppUserDisk

## SYNOPSIS
Menyalin disk pengguna pengguna dari satu kumpulan Azure RemoteApp ke yang lain.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Copy-AzureRemoteAppUserDisk [-SourceCollectionName] <String> [-DestinationCollectionName] <String>
 [-UserUpn] <String> [-OverwriteExistingUserDisk] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Salin-AzureRemoteAppUserDisk** menyalin disk pengguna pengguna dari satu koleksi Azure RemoteApp ke yang lain.

## EXAMPLES

### Contoh 1: Menyalin disk pengguna
```
PS C:\> Copy-AzureRemoteAppUserDisk -DestinationCollectionName "Contoso02" -SourceCollectionName "Contoso01" -UserUpn "PattiFuller@contoso.com" -OverwriteExistingUserDisk
```

Perintah ini menyalin disk pengguna pengguna pengguna Azure Active Directory yang memiliki UPN PattiFuller@contoso.com dari kumpulan Contoso01 ke kumpulan Contoso02.
Jika disk pengguna untuk PattiFuller@contoso.com sudah ada di Contoso02, perintah ini menimpanya.

## PARAMETERS

### -DestinationCollectionName
Menentukan nama kumpulan Azure RemoteApp tujuan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OverwriteExistingUserDisk
Menunjukkan bahwa cmdlet ini menimpa disk pengguna yang sudah ada.

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

### -SourceCollectionName
Menentukan nama kumpulan Azure RemoteApp sumber.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserUpn
Menentukan nama pokok pengguna (UPN) pengguna yang cmdlet ini menyalin disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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

[Hapus-AzureRemoteAppUserDisk](./Remove-AzureRemoteAppUserDisk.md)


