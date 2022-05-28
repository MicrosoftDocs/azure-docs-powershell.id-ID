---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/initialize-azrecoveryservicesdsmove
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Initialize-AzRecoveryServicesDSMove.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Initialize-AzRecoveryServicesDSMove.md
ms.openlocfilehash: 6d9e1e5b565fa6817882d31c5dea6b5564644fed
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145511527"
---
# Initialize-AzRecoveryServicesDSMove

## SYNOPSIS
Menginisialisasi pemindahan DS untuk Copy-AzRecoveryServicesVault.

## SYNTAX

```
Initialize-AzRecoveryServicesDSMove [-DefaultProfile <IAzureContextContainer>] [-SourceVault] <ARSVault>
 [-TargetVault] <ARSVault> [-RetryOnlyFailed] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menginisialisasi pemindahan DS untuk Copy-AzRecoveryServicesVault. Anda wajib menjalankan cmdlet Test-AzRecoveryServicesDSMove sebelum cmdlet ini. Cmdlet ini menghasilkan Id Korelasi yang dapat digunakan sebagai Input untuk Copy-AzRecoveryServicesVault cmdlet. Cmdlet ini berguna untuk skenario pemindahan DS lintas penyewa. 

## EXAMPLES

### Contoh 1: Menginisialisasi Pemindahan DS untuk salinan lintas langganan
```powershell
Set-AzContext -SubscriptionName $targetSubscription
$validated = Test-AzRecoveryServicesDSMove -SourceVault $srcVault -TargetVault $trgVault -Force
Set-AzContext -SubscriptionName $sourceSubscription
if($validated) {
  $corr = Initialize-AzRecoveryServicesDSMove  -SourceVault $srcVault -TargetVault $trgVault
 }
```

Cmdlet pertama menetapkan konteks langganan target. Cmdlet kedua memicu beberapa validasi wajib pada vault target.
Cmdlet ketiga menetapkan konteks langganan sumber.
Kemudian berdasarkan status cmdlet Test-AzRecoveryServicesDSMove, kami mengambil CorrelationId menggunakan cmdlet Initialize-AzRecoveryServicesDSMove. $corr dapat dimasukkan ke cmdlet Salin.

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

### -RetryOnlyFailed
Alihkan parameter untuk mencoba pemindahan data hanya untuk kontainer di vault sumber yang belum dipindahkan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceVault
Objek vault sumber untuk memicu pemindahan data.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.ARSVault
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetVault
Objek vault target tempat data harus dipindahkan.

```yaml
Type: Microsoft.Azure.Commands.RecoveryServices.ARSVault
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.ARSVault

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS
