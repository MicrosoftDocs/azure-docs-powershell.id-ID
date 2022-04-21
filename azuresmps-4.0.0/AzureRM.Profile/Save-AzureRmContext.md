---
external help file: Microsoft.Azure.Commands.Profile.dll-Help.xml
online version: ''
schema: 2.0.0
ms.openlocfilehash: 6ea791c1bdfe6764dea46c764e1ac7255dec7604
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142653364"
---
# Save-AzureRmContext

## SYNOPSIS
Menyimpan informasi autentikasi saat ini untuk digunakan dalam sesi PowerShell lainnya.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Save-AzureRmContext [[-Profile] <AzureRmProfile>] [-Path] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Cmdlet Save-AzureRmContext menyimpan informasi autentikasi saat ini untuk digunakan dalam sesi PowerShell lainnya.

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

Contoh ini menyimpan konteks Azure yang diteruskan ke cmdlet ke file JSON yang disediakan.

## PARAMETERS

### -Paksa
Timpa file yang diberikan jika ada

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

### -Jalur
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
Menentukan konteks Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan konteks, cmdlet ini akan dibaca dari konteks default lokal.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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

## NOTES

## RELATED LINKS

