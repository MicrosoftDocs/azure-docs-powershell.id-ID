---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 77B26360-F22B-457F-BDE3-9920A5736947
online version: ''
schema: 2.0.0
ms.openlocfilehash: 09158ec7fe6809e5f2067b7f44e8b11ebb84d1ffd9d6c41c7999f34d1aa74c69
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419310"
---
# Get-AzureAffinityGroup

## SYNOPSIS
Mendapatkan objek grup afiliasi Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureAffinityGroup [[-Name] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureAffinityGroup** mendapatkan grup Azure affinity.
Objek grup affinity menyertakan nama grup affinity, lokasi, label, deskripsi serta penyimpanan dan layanan yang dihosting yang merupakan bagian dari grup afiliasi.

## EXAMPLES

### Contoh 1: Mendapatkan properti grup affinity
```
PS C:\> Get-AzureAffinityGroup -Name "South01"
```

Perintah ini mendapatkan properti grup affinity bernama South01.

## PARAMETERS

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama grup afiliasi yang akan dapatkan cmdlet ini.
Nama untuk grup afiliasi yang dibuat melalui Portal Manajemen biasanya GUID.
Port Manajemen memperlihatkan label grup kontak.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### AffinityGroup

## CATATAN

## RELATED LINKS

[New-AzureAffinityGroup](./New-AzureAffinityGroup.md)

[Remove-AzureAffinityGroup](./Remove-AzureAffinityGroup.md)

[Set-AzureAffinityGroup](./Set-AzureAffinityGroup.md)


