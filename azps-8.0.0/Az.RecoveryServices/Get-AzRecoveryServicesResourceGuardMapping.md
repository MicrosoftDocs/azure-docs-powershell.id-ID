---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesResourceGuardMapping.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesResourceGuardMapping.md
ms.openlocfilehash: d3ab94c3ff91c41262e97b8db071e80a3efe59d0
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145617728"
---
# Get-AzRecoveryServicesResourceGuardMapping

## SYNOPSIS
Mendapatkan pemetaan penjaga sumber daya yang ditambahkan ke vault layanan pemulihan.

## SYNTAX

```
Get-AzRecoveryServicesResourceGuardMapping [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan pemetaan penjaga sumber daya yang ditambahkan ke vault layanan pemulihan. Cmdlet ini mengambil pemetaan antara vault layanan pemulihan dan resource guard

## EXAMPLES

### Contoh 1 Mengambil pemetaan penjaga sumber daya

```powershell
PS C:\> Get-AzRecoveryServicesResourceGuardMapping -VaultId $vault.ID
```

Perintah di atas mengambil pemetaan yang ada antara vault dan resource guard.

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

### -VaultId
ID ARM dari Vault Layanan Pemulihan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.RecoveryServices.Backup.Models.ResourceGuardProxyBaseResource

## NOTES

## RELATED LINKS
