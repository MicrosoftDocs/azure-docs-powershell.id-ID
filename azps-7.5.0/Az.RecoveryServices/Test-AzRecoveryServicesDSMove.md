---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/test-azrecoveryservicesdsmove
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Test-AzRecoveryServicesDSMove.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Test-AzRecoveryServicesDSMove.md
ms.openlocfilehash: b3b456b59c7dcca91989edeb63df07a33158e09d
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144220274"
---
# Test-AzRecoveryServicesDSMove

## SYNOPSIS
Cmdlet ini melakukan validasi yang diperlukan untuk Pemindahan DS.

## SYNTAX

```
Test-AzRecoveryServicesDSMove [-Force] [-DefaultProfile <IAzureContextContainer>] [-SourceVault] <ARSVault>
 [-TargetVault] <ARSVault> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini melakukan validasi yang diperlukan untuk Pemindahan DS. Cmdlet ini menghasilkan boolean true jika semua validasi berhasil lolos. Anda wajib menjalankan cmdlet ini sebelum Initialize-AzRecoveryServicesDSMove cmdlet. Cmdlet ini berguna untuk skenario pemindahan DS lintas penyewa.

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

### -Force
Memaksa operasi pemindahan data (mencegah dialog konfirmasi).
Parameter ini bersifat opsional.

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

### System.Boolean

## NOTES

## RELATED LINKS
