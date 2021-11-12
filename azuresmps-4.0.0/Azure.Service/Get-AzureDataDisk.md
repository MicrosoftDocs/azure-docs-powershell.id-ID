---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 2A8BE3EB-4929-4B40-82EA-5434C09A5251
online version: ''
schema: 2.0.0
ms.openlocfilehash: c9eda2efd2b944afaa2f7137c507d754879cb535
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427528"
---
# Get-AzureDataDisk

## SYNOPSIS
Mendapatkan disk data Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureDataDisk [[-Lun] <Int32>] -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureDataDisk** mendapatkan objek yang mewakili disk data pada komputer virtual Azure.
Untuk mendapatkan objek disk data tertentu, tentukan nomor unit logika (LUN) disk.

## EXAMPLES

### Contoh 1: Mendapatkan semua disk data untuk mesin virtual
```
PS C:\> Get-AzureVM "ContosoService" -Name "VirtualMachine07" | Get-AzureDataDisk
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine07 dalam layanan yang bernama ContosoService menggunakan cmdlet **Get-AzureVM.**
Perintah tersebut melewati mesin virtual ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini mendapatkan semua disk data untuk komputer virtual ini.

### Contoh 2: Mendapatkan disk data tertentu untuk a vituralvitvittual machinevirtual
```
PS C:\> Get-AzureVM "ContosoService" -Name "VirtualMachine07" | Get-AzureDataDisk -LUN 2
```

Perintah ini mendapatkan mesin virtual bernama VirtualMachine07 dalam layanan yang bernama ContosoService.
Perintah tersebut akan melewati mesin virtual ke cmdlet saat ini.
Cmdlet saat ini mendapatkan disk data yang memiliki LUN 2.

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

### -Lun
Menentukan LUN untuk drive data di komputer virtual.
Nilai valid adalah: 0 sampai 15.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
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
Menentukan objek mesin virtual tempat cmdlet ini mendapatkan disk data.
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

[Get-AzureVM](./Get-AzureVM.md)

[Remove-AzureDataDisk](./Remove-AzureDataDisk.md)

[Set-AzureDataDisk](./Set-AzureDataDisk.md)


