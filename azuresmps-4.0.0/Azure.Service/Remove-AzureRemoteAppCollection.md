---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: 8E67D1A4-4247-4603-8D26-42D6D48FE686
online version: ''
schema: 2.0.0
ms.openlocfilehash: 131bd99c35dfd9917c645ba359ba39f71d0241e4
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422085"
---
# Remove-AzureRemoteAppCollection

## SYNOPSIS
Menghapus koleksi Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureRemoteAppCollection [-CollectionName] <String> [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRemoteAppCollection** menghapus kumpulan Azure RemoteApp.

## EXAMPLES

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRemoteAppCollection](./Get-AzureRemoteAppCollection.md)

[New-AzureRemoteAppCollection](./New-AzureRemoteAppCollection.md)

[Set-AzureRemoteAppCollection](./Set-AzureRemoteAppCollection.md)

[Update-AzureRemoteAppCollection](./Update-AzureRemoteAppCollection.md)


