---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: D563ACF6-6BCD-4463-8731-175BA047A74D
online version: ''
schema: 2.0.0
ms.openlocfilehash: 29993c0305c9e2fc5294826f15d22ef605dbe650
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142312468"
---
# Remove-AzureDataDisk

## SYNOPSIS
Menghapus disk data dari mesin virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureDataDisk [-LUN] <Int32> [-DeleteVHD] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Hapus-AzureDataDisk** menghapus disk data dari mesin virtual Azure.
Secara default, cmdlet ini tidak menghapus blob disk data dari akun penyimpanan.

## EXAMPLES

### Contoh 1: Menghapus disk data
```
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Remove-AzureDataDisk -LUN 0
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine07 dalam layanan bernama ContosoService dengan menggunakan cmdlet **Get-AzureVM** .
Perintah melewati mesin virtual ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini menghapus disk data yang memiliki LUN 0.

### Contoh 2: Menghapus disk data dan file hard disk virtual
```
PS C:\> Get-AzureVM -ServiceName "ContosoService" -Name "VirtualMachine07" | Remove-AzureDataDisk -LUN 0 -DeleteVHD | Update-AzureVM
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine07 dalam layanan bernama ContosoService.
Perintah melewati mesin virtual ke cmdlet saat ini.
Cmdlet saat ini menghapus disk data yang memiliki LUN 0.
Perintah ini menyertakan parameter *DeleteVHD* .
Oleh karena itu, ini juga menghapus hard disk virtual yang mendasar.
Perintah memperbarui mesin virtual untuk mencerminkan perubahan Anda menggunakan cmdlet **Update-AzureVM** .

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
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

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
Nilai yang valid adalah: 0 hingga 15.

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

### -VM
Menentukan objek mesin virtual yang dilampirkan ke disk data.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet **Get-AzureVM** .

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureDataDisk](./Add-AzureDataDisk.md)

[Get-AzureDataDisk](./Get-AzureDataDisk.md)

[Get-AzureVM](./Get-AzureVM.md)

[Set-AzureDataDisk](./Set-AzureDataDisk.md)

[Perbarui-AzureVM](./Update-AzureVM.md)


