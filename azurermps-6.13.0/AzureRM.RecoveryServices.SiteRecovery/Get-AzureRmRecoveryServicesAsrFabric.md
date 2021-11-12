---
external help file: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: AzureRM.RecoveryServices.SiteRecovery
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.recoveryservices.siterecovery/get-azurermrecoveryservicesasrfabric
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices/Commands.RecoveryServices.SiteRecovery/help/Get-AzureRmRecoveryServicesAsrFabric.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices/Commands.RecoveryServices.SiteRecovery/help/Get-AzureRmRecoveryServicesAsrFabric.md
ms.openlocfilehash: db93d022d2abd6d3c6cecfe32b1f82be4483e850
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421601"
---
# Get-AzureRmRecoveryServicesAsrFabric

## SYNOPSIS
Get the details of an Azure Site Recovery Fabric.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Default (Default)
```
Get-AzureRmRecoveryServicesAsrFabric [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByName
```
Get-AzureRmRecoveryServicesAsrFabric -Name <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByFriendlyName
```
Get-AzureRmRecoveryServicesAsrFabric -FriendlyName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmRecoveryServicesAsrFabric** cmdlet gets the properties of a specified Azure Site Recovery Fabric or all Azure Site Recovery Fabrics in a Recovery Service vault.

## EXAMPLES

### Contoh 1
```
PS C:\> $fabrics = Get-AzureRmRecoveryServicesAsrFabric
```

Mengembalikan semua kain Pemulihan Situs Azure di vault.

### Contoh 2
```
PS C:\> $fabric = Get-AzureRmRecoveryServicesAsrFabric -Name xxxx

Name                  : xxxx
FriendlyName          : XXXXXXXXXX
ID                    : /Subscriptions/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX/resourceGroups/canaryexproute/providers/Microsoft.RecoveryServices/vaults/XXXXXXXXXXXXX/replicationFabrics/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
FabricType            : VMware
SiteIdentifier        : XXXXXXXXxxxxxxxxxxx
FabricSpecificDetails : Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRVMWareSpecificDetails
```

Return azure site recovery fabric with name xxxx.

### Contoh 3
```
PS C:\> $fabric = Get-AzureRmRecoveryServicesAsrFabric -FriendlyName XXXXXXXXXX

Name                  : xxxx
FriendlyName          : XXXXXXXXXX
ID                    : /Subscriptions/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX/resourceGroups/canaryexproute/providers/Microsoft.RecoveryServices/vaults/XXXXXXXXXXXXX/replicationFabrics/XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
FabricType            : VMware
SiteIdentifier        : XXXXXXXXxxxxxxxxxxx
FabricSpecificDetails : Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRVMWareSpecificDetails
```

Return azure site recovery fabric with friendly name xxxx.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Search for the ASR fabric by the friendly name of the fabric.

```yaml
Type: System.String
Parameter Sets: ByFriendlyName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Search for the ASR fabric by the name of the fabric.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRFabric, Microsoft.Azure.Commands.RecoveryServices.SiteRecovery, Version=4.0.0.0, Culture=neutral, PublicKeyToken=null]]

## CATATAN

## RELATED LINKS

[New-AzureRmRecoveryServicesAsrFabric](./New-AzureRmRecoveryServicesAsrFabric.md)

[Remove-AzureRmRecoveryServicesAsrFabric](./Remove-AzureRmRecoveryServicesAsrFabric.md)
