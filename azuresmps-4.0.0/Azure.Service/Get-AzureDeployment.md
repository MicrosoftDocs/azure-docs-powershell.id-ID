---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 2171943B-D1AC-45FD-99FD-DD0C14AFC60C
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9f135c05e16bc523d03894ffe689b5863e641009
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142788472"
---
# Get-AzureDeployment

## SYNOPSIS
Mendapatkan detail penyebaran.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

[!INCLUDE [rdfe-deprecation-banner](../../includes/rdfe-deprecation-banner.md)]

## SYNTAX

```
Get-AzureDeployment [-ServiceName] <String> [[-Slot] <String>] [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureDeployment** mendapatkan detail penyebaran Azure.
Tentukan nama layanan Azure dan slot penyebaran.

## EXAMPLES

### Contoh 1: Dapatkan detail untuk penggunaan produksi
```
PS C:\> Get-AzureDeployment -ServiceName "ContosoService"
```

Perintah ini mengembalikan detail penyebaran untuk layanan bernama ContosoService.
Perintah ini tidak menentukan slot.
Oleh karena itu, perintah menggunakan nilai default Produksi.

### Contoh 2: Dapatkan detail untuk penyebaran pementasan
```
PS C:\> Get-AzureDeployment -ServiceName "ContosoService" -Slot "Staging"
```

Perintah ini mengembalikan detail penyebaran pementasan ContosoService.

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

### -ServiceName
Menentukan nama layanan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Menentukan lingkungan penyebaran.
Nilai yang valid adalah: Staging atau Production.
Nilai defaultnya adalah Produksi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureDeploymentEvent](./Get-AzureDeploymentEvent.md)

[Pindahkan-AzureDeployment](./Move-AzureDeployment.md)

[AzureDeployment baru](./New-AzureDeployment.md)

[Hapus-AzureDeployment](./Remove-AzureDeployment.md)

[Set-AzureDeployment](./Set-AzureDeployment.md)


