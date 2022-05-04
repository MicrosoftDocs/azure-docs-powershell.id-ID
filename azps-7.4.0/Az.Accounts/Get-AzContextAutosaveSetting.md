---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/get-azcontextautosavesetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzContextAutosaveSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzContextAutosaveSetting.md
ms.openlocfilehash: 5c673c6412451d3fd13c8a33e1edff90a796f8e2
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144694335"
---
# Get-AzContextAutosaveSetting

## SYNOPSIS
Tampilkan metadata tentang fitur penyimpanan otomatis konteks, termasuk apakah konteks disimpan secara otomatis, dan di mana konteks dan informasi kredensial yang disimpan dapat ditemukan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.accounts/get-azcontextautosavesetting) untuk informasi terbaru.

## SYNTAX

```
Get-AzContextAutosaveSetting [-Scope <ContextModificationScope>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Tampilkan metadata tentang fitur penyimpanan otomatis konteks, termasuk apakah konteks disimpan secara otomatis, dan di mana konteks dan informasi kredensial yang disimpan dapat ditemukan.

## EXAMPLES

### Mendapatkan metadata penyimpanan konteks untuk sesi saat ini
```powershell
Get-AzContextAutosaveSetting
```

```Output
Mode             : Process
ContextDirectory : None
ContextFile      : None
CacheDirectory   : None
CacheFile        : None
Settings         : {}
```

Dapatkan detail tentang apakah dan di mana konteks disimpan.  Dalam contoh di atas, fitur simpan otomatis telah dinonaktifkan.

### Mendapatkan metadata penyimpanan konteks untuk pengguna saat ini
```powershell
Get-AzContextAutosaveSetting -Scope CurrentUser
```

```Output
Mode             : CurrentUser
ContextDirectory : C:\Users\contoso\AppData\Roaming\Windows Azure Powershell
ContextFile      : AzureRmContext.json
CacheDirectory   : C:\Users\contoso\AppData\Roaming\Windows Azure Powershell
CacheFile        : TokenCache.dat
Settings         : {}
```

Dapatkan detail tentang apakah dan di mana konteks disimpan secara default untuk pengguna saat ini.  Perhatikan bahwa ini mungkin berbeda dari pengaturan yang aktif dalam sesi saat ini. Dalam contoh di atas, fitur simpan otomatis telah diaktifkan, dan data disimpan ke lokasi default.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cakupan
Menentukan cakupan perubahan konteks, misalnya, apakah perubahan hanya berlaku untuk proses saat ini, atau untuk semua sesi yang dimulai oleh pengguna ini.

```yaml
Type: Microsoft.Azure.Commands.Profile.Common.ContextModificationScope
Parameter Sets: (All)
Aliases:
Accepted values: Process, CurrentUser

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Common.Authentication.ContextAutosaveSettings

## NOTES

## RELATED LINKS
