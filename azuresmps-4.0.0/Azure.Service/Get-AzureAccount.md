---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 70ADAF16-BC52-47BF-A85A-A84DEACDA027
online version: ''
schema: 2.0.0
ms.openlocfilehash: e73397e924f90f4936bf53367a532a78ad47cbb4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142335828"
---
# Get-AzureAccount

## SYNOPSIS
Mendapatkan akun Azure yang tersedia untuk Azure PowerShell.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureAccount [-Name <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureAccount** mendapatkan akun Azure yang tersedia untuk Windows PowerShell.
Agar akun Anda tersedia untuk Windows PowerShell, gunakan cmdlet **Add-AzureAccount** atau **Import-PublishSettingsFile**.

## EXAMPLES

### Contoh 1: Dapatkan semua akun
```
PS C:\> Get-AzureAccount

Name                         ActiveDirectories
----                         -----------------
contosoadmin@outlook.com     {{ ActiveDirectoryTenantId = abcde5cd-bcc3-441a-bd86-e6a...
contosotest1@outlook.com     {{ ActiveDirectoryTenantId = aaeabcde-386c-4466-bf70-794...
```

Perintah ini mendapatkan semua akun yang terkait dengan pengguna tertentu.

### Contoh 2: Dapatkan akun menurut nama
```
PS C:\> Get-AzureAccount -Name contosoadmin@outlook.com

Name                         ActiveDirectories
----                         -----------------
contosoadmin@outlook.com     {{ ActiveDirectoryTenantId = abcde5cd-bcc3-441a-bd86-e6a...
```

Perintah ini mendapatkan akun ContosoAdmin.

## PARAMETERS

### -Nama
Hanya mendapatkan akun yang ditentukan.
Defaultnya adalah semua akun yang tersedia untuk Windows PowerShell.
Masukkan nama akun.
Nilai **Nama** peka huruf besar/kecil.
Wildcard tidak diizinkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Anda tidak dapat menyalurkan input ke cmdlet ini.

## OUTPUTS

### Tidak
Cmdlet ini tidak mengembalikan output apa pun.

## CATATAN

## RELATED LINKS

[Add-AzureAccount](./Add-AzureAccount.md)

[Get-AzurePublishSettingsFile](./Get-AzurePublishSettingsFile.md)

[Impor-AzurePublishSettingsFile](./Import-AzurePublishSettingsFile.md)

[Hapus-AzureAccount](./Remove-AzureAccount.md)


