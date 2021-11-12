---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 7180CAC6-BFC1-4A18-A754-83D5F05C5BEF
online version: ''
schema: 2.0.0
ms.openlocfilehash: 59ce7748bcaf74eb7552a8a5c80fec4dacc5cc51250ffbf0d9baa0ca6df88112
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418855"
---
# Import-AzureVM

## SYNOPSIS
Mengimpor status mesin virtual Azure dari file.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Import-AzureVM [-Path] <String> [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Import-AzureVM** mengimpor status mesin virtual yang disimpan sebelumnya dari file XML.
Cmdlet ini berguna saat Anda ingin membuat mesin virtual dari data yang diimpor.

Menjalankan **Export-AzureVM,** diikuti oleh **Remove-AzureVM** lalu **Import-AzureVM** untuk membuat ulang mesin virtual dapat menyebabkan mesin virtual yang dihasilkan memiliki alamat IP berbeda dari aslinya.

## EXAMPLES

### Contoh 1: Mengimpor status mesin virtual
```
PS C:\> Import-AzureVM -Path "C:\VMstate.xml" | New-AzureVM -ServiceName "ContosoService02"
```

Perintah ini mengimpor status mesin virtual dari file VMstate.xml, lalu membuat mesin virtual di layanan awan yang ditentukan.

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

### -Path
Menentukan jalur file dengan status mesin virtual yang disimpan sebelumnya.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[Export-AzureVM](./Export-AzureVM.md)

[New-AzureVM](./New-AzureVM.md)


