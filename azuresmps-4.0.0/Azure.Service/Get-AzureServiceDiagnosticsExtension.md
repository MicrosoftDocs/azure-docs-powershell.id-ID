---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 235DD5D7-BE24-4FBE-88E2-40D1943ED155
online version: ''
schema: 2.0.0
ms.openlocfilehash: dd308e450b34c3f6cc7f7c09fd24a5d27102f078
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142981307"
---
# Get-AzureServiceDiagnosticsExtension

## SYNOPSIS
Mendapatkan ekstensi diagnostik layanan cloud yang diterapkan pada semua peran atau peran bernama pada slot penyebaran tertentu.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

[!INCLUDE [rdfe-deprecation-banner](../../includes/rdfe-deprecation-banner.md)]

## SYNTAX

```
Get-AzureServiceDiagnosticsExtension [[-ServiceName] <String>] [[-Slot] <String>] [[-Role] <String[]>]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureServiceDiagnosticsExtension** mendapatkan ekstensi diagnostik layanan cloud yang diterapkan pada semua peran atau peran bernama di slot penyebaran tertentu.

## EXAMPLES

### Contoh 1: Dapatkan ekstensi diagnostik layanan 
```
PS C:\> Get-AzureServiceDiagnosticsExtension -ServiceName $Svc
```

Perintah ini mendapatkan diagnostik layanan untuk layanan, di semua peran.

## PARAMETERS

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

### -Peran
Menentukan array peran.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceName
Menentukan nama layanan Azure dari penyebaran.

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

### -Slot
Menentukan lingkungan penyebaran untuk diubah.
Nilai yang dapat diterima untuk parameter ini adalah: Produksi atau Staging.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Remove-AzureServiceDiagnosticsExtension](./Remove-AzureServiceDiagnosticsExtension.md)

[Set-AzureServiceDiagnosticsExtension](./Set-AzureServiceDiagnosticsExtension.md)


