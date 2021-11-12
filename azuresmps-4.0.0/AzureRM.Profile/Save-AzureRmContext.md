---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: ''
schema: 2.0.0
ms.openlocfilehash: b7877795c52b3e1f568d5756eb6329046741c18fb6a0e3a249f1a9200d0911b4
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417635"
---
# Save-AzureRmContext

## SYNOPSIS
Menyimpan informasi autentikasi saat ini untuk digunakan di sesi PowerShell lainnya.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Save-AzureRmContext [[-Profile] <AzureRmProfile>] [-Path] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Cmdlet Save-AzureRmContext menyimpan informasi autentikasi saat ini untuk digunakan di sesi PowerShell lainnya.

## EXAMPLES

### Contoh 1: Menyimpan konteks sesi saat ini
```
PS C:\> Add-AzureRmAccount
PS C:\> Save-AzureRmContext -Path C:\test.json
```

Contoh ini menyimpan konteks Azure sesi saat ini ke file JSON yang disediakan.

### Contoh 2: Menyimpan konteks tertentu
```
PS C:\> Save-AzureRmContext -Profile (Add-AzureRmAccount) -Path C:\test.json
```

Contoh ini menyimpan konteks Azure yang disampaikan ke cmdlet ke file JSON yang disediakan.

## PARAMETERS

### -Force
Menimpa file tertentu jika ada

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Menentukan jalur file untuk menyimpan informasi autentikasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan konteks Azure yang dibaca cmdlet ini.
Jika Anda tidak menentukan konteksnya, cmdlet ini akan membaca dari konteks default lokal.

```yaml
Type: AzureRmProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Azure.Commands.Common.Authentication.Models.AzureRMProfile

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.PSAzureProfile

## CATATAN

## RELATED LINKS

