---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: 000B2335-E374-47CC-8165-40AE807C090F
online version: ''
schema: 2.0.0
ms.openlocfilehash: 5a9661e474ba8dbf11eea8a6252688a5056b2f42
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422074"
---
# Remove-AzureRemoteAppVNet

## SYNOPSIS
Menghapus jaringan virtual Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureRemoteAppVNet -VNetName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRemoteAppVNet** menghapus jaringan virtual Azure RemoteApp.

## EXAMPLES

### Contoh 1: Menghapus jaringan virtual tertentu
```
PS C:\> Remove-AzureRemoteAppVnet -VNetName "ContosoVNet"
```

Perintah ini menghapus jaringan virtual yang bernama ContosoVNet.

## PARAMETERS

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
Menentukan nama jaringan virtual Azure RemoteApp yang akan dihapus.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRemoteAppVNet](./Get-AzureRemoteAppVNet.md)

[Set-AzureRemoteAppVNet](./Set-AzureRemoteAppVNet.md)


