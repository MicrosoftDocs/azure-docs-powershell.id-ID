---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: FB5CD696-108D-4A3E-8983-1C6562E8795A
online version: ''
schema: 2.0.0
ms.openlocfilehash: 29e1f806e2ef4d7bff7b7cb9c5de358002e7f44e
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421173"
---
# Add-AzureWebRole

## SYNOPSIS
Menambahkan peran pekerja web.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureWebRole [-TemplateFolder <String>] [-Name <String>] [-Instances <Int32>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Add-AzureWebRole** menambahkan peran pekerja web.

## EXAMPLES

### Contoh 1: Tambahkan peran default
```
PS C:\> Add-AzureWebRole
```

Perintah ini menambahkan peran web yang memiliki konfigurasi default Webrole1 sebagai nama dan contoh tunggal.

### Contoh 2: Tambahkan peran dengan nama
```
PS C:\> Add-AzureWebRole -Name "MyWebRole"
```

Perintah ini menambahkan peran web tunggal bernama MyWebRole ke aplikasi saat ini.

### Contoh 3: Tambahkan peran dengan nama dan jumlah contoh
```
PS C:\> Add-AzureWebRole -Name "MyWebRole" -Instance 2
```

Perintah ini menambahkan peran web bernama MyWebRole ke aplikasi saat ini.
Cmdlet memiliki jumlah contoh peran 2.

### Contoh 4: Tambahkan peran dengan nama dan templat
```
PS C:\> Add-AzureWebRole -Name "MyWebRole" -TemplateFolder ".\MyWebTemplateFolder"
```

Perintah ini menambahkan peran web tunggal bernama MyWebRole ke aplikasi saat ini.
Perintah menentukan folder bernama MyWebTemplateFolder sebagai templat foldercacah.

## PARAMETERS

### -Contoh
Menentukan jumlah instans.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: i

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama peran web.

```yaml
Type: String
Parameter Sets: (All)
Aliases: n

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

### -TemplateFolder
Menentukan folder templat.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureWorkerRole](./Add-AzureWorkerRole.md)

[New-AzureRoleTemplate](./New-AzureRoleTemplate.md)


