---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 95DCD2EC-8327-4A46-B624-289D0A28F7EA
online version: ''
schema: 2.0.0
ms.openlocfilehash: 0ba46006c203eabdf205c495be664f8dde80dc25
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424139"
---
# Get-AzureDisk

## SYNOPSIS
Dapatkan informasi tentang disk di penyimpanan disk Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureDisk [[-DiskName] <String>] [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureDisk** mendapatkan informasi tentang disk yang disimpan di penyimpanan disk Azure untuk langganan saat ini.
Cmdlet ini mengembalikan daftar informasi untuk semua disk dalam penyimpanan.
Untuk menampilkan informasi untuk disk tertentu, tentukan nama disk.

## EXAMPLES

### Contoh 1: Mendapatkan informasi tentang disk
```
PS C:\> Get-AzureDisk -DiskName "ContosoDataDisk"
```

Perintah ini mendapatkan data informasi tentang disk yang bernama ContosoDataDisk dari penyimpanan disk.

### Contoh 2: Mendapatkan informasi tentang semua disk
```
PS C:\> Get-AzureDisk
```

Perintah ini mendapatkan informasi tentang semua disk dalam penyimpanan disk.

### Contoh 3: Mendapatkan informasi tentang disk
```
PS C:\> Get-AzureDisk | Where-Object {$_.AttachedTo -eq $Null } | Format-Table -AutoSize -Property "DiskName","DiskSizeInGB","MediaLink"
```

Perintah ini mendapatkan data untuk semua disk di repositori disk yang saat ini tidak terhubung ke mesin virtual.
Perintah tersebut mendapatkan informasi tentang semua disk, dan meneruskan setiap objek ke cmdlet **Where-Object.**
Cmdlet tersebut menghasilkan disk apa pun yang tidak memiliki nilai $Null untuk **properti AttachedTo.**
Perintah memformat daftar sebagai tabel menggunakan cmdlet **Format-Tabel.**

## PARAMETERS

### -DiskName
Menentukan nama disk di penyimpanan disk tempat cmdlet ini mendapatkan informasi.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureDisk](./Add-AzureDisk.md)

[Remove-AzureDisk](./Remove-AzureDisk.md)

[Update-AzureDisk](./Update-AzureDisk.md)


