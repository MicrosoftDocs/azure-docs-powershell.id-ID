---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: 58DABEB0-D3B6-478B-9B83-80E4C67A7792
online version: ''
schema: 2.0.0
ms.openlocfilehash: 1b35e18a0643105e80a6e8009631d178506d6b6f
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428107"
---
# Get-AzureRemoteAppVNet

## SYNOPSIS
Mengambil informasi tentang jaringan virtual Azure RemoteApp di Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRemoteAppVNet [[-VNetName] <String>] [-IncludeSharedKey] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRemoteAppVNet** mengambil informasi tentang jaringan virtual Azure RemoteApp di Microsoft Azure.
Cmdlet ini mengembalikan objek yang berisi informasi tentang jaringan virtual tertentu.
Jika tidak ada jaringan virtual yang ditentukan, cmdlet ini akan mengembalikan informasi tentang semua jaringan virtual dalam langganan saat ini.

## EXAMPLES

### Contoh 1: Mengambil informasi tentang jaringan virtual
```
PS C:\> Get-AzureRemoteAppVNet -VNetName "ContosoVNet"
```

Perintah ini mendapatkan informasi tentang jaringan virtual bernama ContosoVNet.

## PARAMETERS

### -IncludeSharedKey
Mengindikasikan bahwa cmdlet ini menyertakan nilai kunci bersama dalam informasi yang diambilnya tentang jaringan virtual.

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

### -VNetName
Menentukan nama jaringan virtual Azure RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Set-AzureRemoteAppVNet](./Set-AzureRemoteAppVNet.md)


