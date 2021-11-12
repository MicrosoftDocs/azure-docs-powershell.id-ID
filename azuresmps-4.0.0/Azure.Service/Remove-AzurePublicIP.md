---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 9EA98944-1923-4573-991E-3B9CA21004BB
online version: ''
schema: 2.0.0
ms.openlocfilehash: 655679da8cf8f63f23c010f13e1cc2293d5e5baf
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422079"
---
# Remove-AzurePublicIP

## SYNOPSIS
Menghapus konfigurasi IP publik dari komputer virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzurePublicIP [[-PublicIPName] <String>] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzurePublicIP** menghapus konfigurasi IP publik dari komputer virtual Azure.

## EXAMPLES

### Contoh 1: Hapus konfigurasi IP publik
```
PS C:\> Get-AzureVM -ServiceName "FTPInAzure" -Name "FTPInstance" | Remove-AzurePublicIP | Update-AzureVM
```

Perintah ini mendapatkan mesin virtual yang bernama FTPInstance dalam layanan yang bernama FTPInAzure menggunakan cmdlet **Get-AzureVM.**
Perintah itu melewati mesin virtual itu ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet saat ini menghapus konfigurasi IP publik dari komputer virtual.
Perintah tersebut melewati mesin virtual ke cmdlet **Update-AzureVM,** yang menerapkan perubahan Anda.

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

### -PublicIPName
Menentukan nama IP Publik.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan komputer virtual tempat cmdlet ini menghapus konfigurasi IP Publik.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.commands.ServiceManagement.Model.IPersistentVM

## CATATAN

## RELATED LINKS

[Get-AzurePublicIP](./Get-AzurePublicIP.md)

[Get-AzureVM](./Get-AzureVM.md)

[Set-AzurePublicIP](./Set-AzurePublicIP.md)

[Update-AzureVM](./Update-AzureVM.md)


