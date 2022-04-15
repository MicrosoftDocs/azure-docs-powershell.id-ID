---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.SiteRecovery.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/get-azrecoveryservicesasrvaultcontext
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesAsrVaultContext.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Get-AzRecoveryServicesAsrVaultContext.md
ms.openlocfilehash: 1eddb803ea4568ed1dcb0da5951db2aa827f2575
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141949677"
---
# Get-AzRecoveryServicesAsrVaultContext

## SYNOPSIS
Mendapatkan informasi pengaturan vault ASR untuk kubah Layanan Pemulihan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/get-azrecoveryservicesasrvaultcontext) untuk informasi terbaru.

## SYNTAX

```
Get-AzRecoveryServicesAsrVaultContext [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzRecoveryServicesAsrVaultContext** mendapatkan informasi pengaturan vault ASR yang terkait dengan kubah Layanan Pemulihan.

## EXAMPLES

### Contoh 1
```
PS C:\> $VaultSettings = Get-AzRecoveryServicesAsrVaultContext
```

Mendapatkan pengaturan vault ASR untuk kubah Layanan Pemulihan yang saat ini aktif(dalam sesi PowerShell).

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRVaultSettings

## CATATAN

## RELATED LINKS
