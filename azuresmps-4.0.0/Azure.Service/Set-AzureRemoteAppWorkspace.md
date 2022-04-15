---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: 608B4B5E-5DB2-4291-966C-0B25F8D4FA13
online version: ''
schema: 2.0.0
ms.openlocfilehash: 65b4cba0b710dfd8c3cb5e59e52aec955525c187
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142312231"
---
# Set-AzureRemoteAppWorkspace

## SYNOPSIS
Mengatur properti ruang kerja Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureRemoteAppWorkspace [-WorkspaceName] <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRemoteAppWorkspace** mengatur properti ruang kerja Azure RemoteApp.

## EXAMPLES

### Contoh 1: Mengatur nama ruang kerja
```
PS C:\> Set-AzureRemoteAppWorkspace -WorkspaceName "Contoso Work Applications"

TrackingId
----------
12345
```

Perintah ini mengatur nama ruang kerja Azure RemoteApp ke Aplikasi Kerja Contoso.

## PARAMETERS

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

### -Nama Ruang Kerja
Menentukan nama ruang kerja Azure RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN
* Semua koleksi Azure RemoteApp untuk langganan tertentu ada di dalam ruang kerja bersama.

## RELATED LINKS

[Get-AzureRemoteAppWorkspace](./Get-AzureRemoteAppWorkspace.md)


