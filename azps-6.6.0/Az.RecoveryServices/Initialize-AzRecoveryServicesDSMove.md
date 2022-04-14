---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/initialize-azrecoveryservicesdsmove
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Initialize-AzRecoveryServicesDSMove.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Initialize-AzRecoveryServicesDSMove.md
ms.openlocfilehash: 1e7c83834c39fe59a086f593d1f6cb395dd0f484
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142122965"
---
# Initialize-AzRecoveryServicesDSMove

## SYNOPSIS
Menginisialisasi pemindahan DS untuk Copy-AzRecoveryServicesVault.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/initialize-azrecoveryservicesdsmove) untuk informasi terbaru.

## SYNTAX

```
Initialize-AzRecoveryServicesDSMove [-DefaultProfile <IAzureContextContainer>] [-SourceVault] <ARSVault>
 [-TargetVault] <ARSVault> [-RetryOnlyFailed] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menginisialisasi pemindahan DS untuk Copy-AzRecoveryServicesVault. Anda harus menjalankan cmdlet Test-AzRecoveryServicesDSMove sebelum cmdlet ini. Cmdlet ini menghasilkan Id Korlasi yang dapat digunakan sebagai Input untuk Copy-AzRecoveryServicesVault cmdlet. Cmdlet ini berguna untuk skenario perpindahan DS penyewa silang. 

## EXAMPLES

### Contoh 1: Inisialisasi Pemindahan DS untuk salinan lintas langganan
```powershell
PS C:\> Set-AzContext -SubscriptionName $targetSubscription
PS C:\> $validated = Test-AzRecoveryServicesDSMove -SourceVault $srcVault -TargetVault $trgVault -Force
PS C:\> Set-AzContext -SubscriptionName $sourceSubscription
PS C:\> if($validated) {
>>  $corr = Initialize-AzRecoveryServicesDSMove  -SourceVault $srcVault -TargetVault $trgVault
>> }
```

Cmdlet pertama menetapkan konteks langganan target. Cmdlet kedua memicu beberapa validasi wajib pada kubah target.
Cmdlet ketiga mengatur konteks langganan sumber.
Kemudian berdasarkan Test-AzRecoveryServicesDSMove cmdlet state, kami mengambil CorrelationId menggunakan cmdlet Initialize-AzRecoveryServicesDSMove. $corr dapat diinput ke cmdlet Salin.

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
Alihkan parameter untuk mencoba pemindahan data hanya untuk kontainer dalam kubah sumber yang belum dipindahkan.

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
Objek kubah sumber untuk memicu perpindahan data.

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
Objek kubah target tempat data harus dipindahkan.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.ARSVault

## OUTPUTS

### System.String

## CATATAN

## RELATED LINKS
