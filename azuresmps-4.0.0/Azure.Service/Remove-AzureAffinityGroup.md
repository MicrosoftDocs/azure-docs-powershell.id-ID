---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 29602F63-A05B-45AF-8DD8-5EBBF4C33FCE
online version: ''
schema: 2.0.0
ms.openlocfilehash: 22c0abb5afdb09ba1b799a28e642d4730efc134f
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427474"
---
# Remove-AzureAffinityGroup

## SYNOPSIS
Menghapus grup afiliasi dalam langganan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureAffinityGroup [-Name] <String> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureAffinityGroup** menghapus grup Azure affinity dalam langganan saat ini.
Anda tidak bisa menghapus grup afiliasi yang memiliki semua anggota.
Anda harus terlebih dahulu menghapus semua anggota grup afiliasi.

## EXAMPLES

### Contoh 1: Menghapus grup afiliasi
```
PS C:\> Remove-AzureAffinityGroup -Name "South01"
```

Perintah ini menghapus grup affinity South01 dalam langganan saat ini.

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
Menentukan nama grup afiliasi yang dihapus cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

## CATATAN

## RELATED LINKS

[Get-AzureAffinityGroup](./Get-AzureAffinityGroup.md)

[New-AzureAffinityGroup](./New-AzureAffinityGroup.md)

[Set-AzureAffinityGroup](./Set-AzureAffinityGroup.md)


