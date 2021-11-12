---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 3422EFD0-88DC-4DF0-868C-5C63C9FA95EF
online version: ''
schema: 2.0.0
ms.openlocfilehash: 072d49cceb4f172c85172aa8d749fe7983b52a0f
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421168"
---
# Disable-AzureWebsiteApplicationDiagnostic

## SYNOPSIS
Menonaktifkan diagnostik aplikasi untuk situs web Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Disable-AzureWebsiteApplicationDiagnostic [-PassThru] [-File] [-TableStorage] [-BlobStorage] [-Name <String>]
 [-Slot <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Menonaktifkan diagnostik aplikasi untuk situs web Azure.
Menonaktifkan pembuatan log yang dikonfigurasi untuk disimpan pada sistem file atau di Azure.

## EXAMPLES

### Contoh 1: Nonaktifkan file pembuatan log aplikasi
```
PS C:\> Disable-AzureWebsiteApplicationDiagnostic -Name MyWebsite -File
```

Contoh berikut ini menonaktifkan pembuatan log aplikasi pada sistem file.

### Contoh 2: Menonaktifkan pembuatan log menggunakan penyimpanan Azure
```
PS C:\> Disable-AzureWebsiteApplicationDiagnostic -Name MyWebsite -Storage
```

Contoh berikut ini menonaktifkan pembuatan log aplikasi menggunakan penyimpanan.

## PARAMETERS

### -BlobStorage
```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -File
Menentukan bahwa Anda ingin menggunakan sistem file untuk menyimpan file log.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama situs web.

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

### -PassThru
Bendera untuk mengembalikan true jika berhasil.

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

### -Slot
Menentukan nama slot.

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

### -TableStorage
```yaml
Type: SwitchParameter
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

[Enable-AzureWebsiteApplicationDiagnostic](./Enable-AzureWebsiteApplicationDiagnostic.md)

[Get-AzureWebsite](./Get-AzureWebsite.md)

[New-AzureWebsite](./New-AzureWebsite.md)

[Remove-AzureWebsite](./Remove-AzureWebsite.md)

[Start-AzureWebsite](./Start-AzureWebsite.md)


