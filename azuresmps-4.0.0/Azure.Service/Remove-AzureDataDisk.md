---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: D563ACF6-6BCD-4463-8731-175BA047A74D
online version: ''
schema: 2.0.0
ms.openlocfilehash: 29993c0305c9e2fc5294826f15d22ef605dbe650
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423197"
---
# Remove-AzureDataDisk

## SYNOPSIS
Menghapus disk data dari komputer virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureDataDisk [-LUN] <Int32> [-DeleteVHD] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureDataDisk** menghapus disk data dari komputer virtual Azure.
Secara default, cmdlet ini tidak menghapus blob disk data dari akun penyimpanan.

## EXAMPLES

### Contoh 1: Menghapus disk data
```
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Remove-AzureDataDisk -LUN 0
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine07 dalam layanan yang bernama ContosoService menggunakan cmdlet **Get-AzureVM.**
Perintah tersebut melewati mesin virtual ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini akan menghapus disk data yang memiliki LUN 0.

### Contoh 2: Menghapus disk data dan file hard disk virtual
```
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Remove-AzureDataDisk -LUN 0 -DeleteVHD | Update-AzureVM
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine07 dalam layanan yang bernama ContosoService.
Perintah tersebut akan melewati mesin virtual ke cmdlet saat ini.
Cmdlet saat ini akan menghapus disk data yang memiliki LUN 0.
Perintah ini menyertakan parameter *DeleteVHD.*
Oleh karena itu, menghapus hard disk virtual yang mendasarinya.
Perintah memperbarui mesin virtual agar mencerminkan perubahan Anda menggunakan cmdlet **Update-AzureVM.**

## PARAMETERS

### -DeleteVHD
Menunjukkan bahwa cmdlet ini menghapus disk data dan hard disk virtual (VHD) dari penyimpanan blob.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -LUN
Menentukan nomor unit logika (LUN) untuk drive data di mesin virtual.
Nilai valid adalah: 0 sampai 15.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

### -VM
Menentukan objek mesin virtual yang dilampirkan ke disk data.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet **Get-AzureVM.**

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

## CATATAN

## RELATED LINKS

[Add-AzureDataDisk](./Add-AzureDataDisk.md)

[Get-AzureDataDisk](./Get-AzureDataDisk.md)

[Get-AzureVM](./Get-AzureVM.md)

[Set-AzureDataDisk](./Set-AzureDataDisk.md)

[Update-AzureVM](./Update-AzureVM.md)


