---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: E246C177-EAEE-4D7A-A544-664F47862FC7
online version: ''
schema: 2.0.0
ms.openlocfilehash: 8a09ff561f8877199ec08a3a39fbe6de9173c170b1d6cf6c9e7d85d2a73ca3ff
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132414783"
---
# Remove-AzureSBAuthorizationRule

## SYNOPSIS
Menghapus aturan otorisasi Bus Layanan yang sudah ada.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### EntitySAS
```
Remove-AzureSBAuthorizationRule -Name <String> -Namespace <String> -EntityName <String>
 -EntityType <ServiceBusEntityType> [-PassThru] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Kumpulan nama
```
Remove-AzureSBAuthorizationRule -Name <String> -Namespace <String> [-PassThru] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Menghapus aturan otorisasi Bus Layanan yang sudah ada.

[!INCLUDE [sb-deprecation.md](../include/sb-deprecation.md)]

## EXAMPLES

### Contoh 1: Hapus aturan otorisasi di tingkat ruang nama
```
PS C:\> Remove-AzureSBAuthorizationRule -Name MyRule -Namespace MyNamespace
```

Menghapus aturan otorisasi MyRule dari MyNamespace.

### Contoh 2: Hapus aturan otorisasi untuk Antrean
```
PS C:\> Remove-AzureSBAuthorizationRule -Name MyRule -Namespace MyNamespace -EntityName MyEntity -EntityType Queue
```

Menghapus aturan otorisasi yang disebut MyRule untuk MyEntity Queue di MyNamespace.

## PARAMETERS

### -EntityName
Nama entitas untuk diterapkan aturan di.

```yaml
Type: String
Parameter Sets: EntitySAS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EntityType
Tipe entitas (Queue, Topic, Relay, NotificationHub).

```yaml
Type: ServiceBusEntityType
Parameter Sets: EntitySAS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama aturan otorisasi unik.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Namespace
Nama ruang nama untuk menerapkan aturan otorisasi.
Jika tidak ada EntityName yang menyediakan aturan akan berada di tingkat ruang nama.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Menunjukkan bahwa cmdlet ini mengembalikan objek yang mewakili item tempat operasinya.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSBAuthorizationRule](./Get-AzureSBAuthorizationRule.md)

[New-AzureSBAuthorizationRule](./New-AzureSBAuthorizationRule.md)

[Set-AzureSBAuthorizationRule](./Set-AzureSBAuthorizationRule.md)


