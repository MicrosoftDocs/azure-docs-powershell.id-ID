---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: D6D54096-670D-43E4-93EB-24C8FBA199A4
online version: ''
schema: 2.0.0
ms.openlocfilehash: 08beb113cb4a5a805a64acde330c033a485fac32
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142980587"
---
# Remove-AzureDeployment

## SYNOPSIS
Menghapus penyebaran layanan awan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

[!INCLUDE [rdfe-deprecation-banner](../../includes/rdfe-deprecation-banner.md)]

## SYNTAX

```
Remove-AzureDeployment [-ServiceName] <String> [-Slot] <String> [-DeleteVHD] [-Force]
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureDeployment** menghapus penyebaran layanan cloud Azure.
Untuk menghapus penyebaran, tangguhkan terlebih dahulu.

## EXAMPLES

### Contoh 1: Menghapus penyebaran
```
PS C:\> Remove-AzureDeployment -ServiceName "ContosoService"
```

Perintah ini menghapus penyebaran layanan Azure bernama ContosoService.
Karena perintah ini tidak menentukan slot, perintah ini menghapus layanan dari lingkungan produksi.

### Contoh 2: Menghapus penyebaran dan hard disk virtual
```
PS C:\> Remove-AzureDeployment -ServiceName "ContosoService" -DeleteVHD
```

Perintah ini menghapus penyebaran layanan bernama ContosoService dari lingkungan produksi.
Perintah ini juga menghapus hard disk virtual yang mendasar.

## PARAMETERS

### -DeleteVHD
Menentukan bahwa cmdlet ini menghapus penyebaran dan hard disk virtual (VHD) dari penyimpanan blob.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Menentukan nama layanan yang cmdletnya menghapus penyebaran.

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
Menentukan lingkungan penyebaran tempat cmdlet ini menghapus penyebaran.
Nilai yang valid adalah: Pementasan dan Produksi.
Nilai defaultnya adalah Produksi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ManagementOperationContext

## NOTES

## RELATED LINKS

[Get-AzureDeployment](./Get-AzureDeployment.md)

[Get-AzureDeploymentEvent](./Get-AzureDeploymentEvent.md)

[Pindahkan-AzureDeployment](./Move-AzureDeployment.md)

[AzureDeployment baru](./New-AzureDeployment.md)

[Set-AzureDeployment](./Set-AzureDeployment.md)


