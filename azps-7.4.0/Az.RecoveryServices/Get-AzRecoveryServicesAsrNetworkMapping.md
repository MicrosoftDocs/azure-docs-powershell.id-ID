---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesasrnetworkmapping
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesAsrNetworkMapping.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesAsrNetworkMapping.md
ms.openlocfilehash: 6734c9c8b828a9dc171b92a1d2d811bab230b3ef
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142172258"
---
# Get-AzRecoveryServicesAsrNetworkMapping

## SYNOPSIS
Mendapatkan informasi tentang pemetaan jaringan Site Recovery untuk kubah saat ini.

## SYNTAX

### ByObject (Default)
```
Get-AzRecoveryServicesAsrNetworkMapping [-Name <String>] -Network <ASRNetwork>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByFabricObject
```
Get-AzRecoveryServicesAsrNetworkMapping [-Name <String>] -PrimaryFabric <ASRFabric>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzRecoveryServicesAsrNetworkMapping** mendapatkan informasi tentang pemetaan jaringan Azure Site Recovery untuk kubah Layanan Pemulihan.

## EXAMPLES

### Contoh 1
```powershell
$Networkmappings = Get-AzRecoveryServicesAsrNetworkMapping -Network $Network
```

Mendapatkan semua pemetaan jaringan untuk Jaringan yang lolos.

### Contoh 2
```powershell
$primaryFabric = Get-AzRecoveryServicesAsrFabric -Name xxxx
$Networkmappings = Get-AzRecoveryServicesAsrNetworkMapping -Name $networkMappingName -PrimaryFabric $primaryFabric
```

Mendapatkan pemetaan jaringan dengan nama yang disediakan dalam kain pemulihan situs azure tertentu.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.


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

### -Nama
Nama objek pemetaan jaringan ASR untuk didapatkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jaringan
Dapatkan pemetaan jaringan ASR yang terkait dengan objek ASR jaringan yang ditentukan.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRNetwork
Parameter Sets: ByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PrimaryFabric
Dapatkan pemetaan jaringan ASR yang sesuai dengan objek kain utama yang ditentukan.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRFabric
Parameter Sets: ByFabricObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRNetwork

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRFabric

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRNetworkMapping

## CATATAN

## RELATED LINKS

[New-AzRecoveryServicesAsrNetworkMapping](./New-AzRecoveryServicesAsrNetworkMapping.md)

[Remove-AzRecoveryServicesAsrNetworkMapping](./Remove-AzRecoveryServicesAsrNetworkMapping.md)
