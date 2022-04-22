---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 3F939FE9-5D42-4EA1-90DC-E6D60158CADE
online version: ''
schema: 2.0.0
ms.openlocfilehash: 914790a311588d0c182dd16ee6c1d547f3b9e658
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142980569"
---
# Remove-AzureInternalLoadBalancer

## SYNOPSIS
Menghapus konfigurasi load balancer internal.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureInternalLoadBalancer [-ServiceName] <String> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureInternalLoadBalancer** menghapus konfigurasi penyeimbang muatan internal dari layanan Azure.
Jika titik akhir saat ini merujuk ke penyeimbang beban internal, cmdlet ini tidak dapat menghapus konfigurasi.

## EXAMPLES

### Contoh 1: Menghapus konfigurasi load balancer internal
```
PS C:\> Remove-AzureInternalLoadBalancer -ServiceName "ContosoService"
```

Perintah ini menghapus konfigurasi load balancer internal untuk layanan bernama ContosoService.

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
Menentukan nama layanan tempat cmdlet ini menghapus penyeimbang muatan internal.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.Common.ManagementOperationContext

## NOTES

## RELATED LINKS

[Add-AzureInternalLoadBalancer](./Add-AzureInternalLoadBalancer.md)

[Get-AzureInternalLoadBalancer](./Get-AzureInternalLoadBalancer.md)

[Baru-AzureInternalLoadBalancerConfig](./New-AzureInternalLoadBalancerConfig.md)

[Set-AzureInternalLoadBalancer](./Set-AzureInternalLoadBalancer.md)


