---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/test-azrecoveryservicesdsmove
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Test-AzRecoveryServicesDSMove.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Test-AzRecoveryServicesDSMove.md
ms.openlocfilehash: c3c3099d102c6a185d0e23ff40af6c2e49369f30
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140050475"
---
# Test-AzRecoveryServicesDSMove

## SYNOPSIS
Cmdlet ini menjalankan validasi yang diperlukan untuk Pemindahan DS.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.recoveryservices/test-azrecoveryservicesdsmove) untuk informasi terkini.

## SYNTAX

```
Test-AzRecoveryServicesDSMove [-Force] [-DefaultProfile <IAzureContextContainer>] [-SourceVault] <ARSVault>
 [-TargetVault] <ARSVault> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet ini menjalankan validasi yang diperlukan untuk Pemindahan DS. Cmdlet ini menghasilkan boolean true jika semua validasi berhasil melewatinya. Cmdlet ini wajib dijalankan sebelum Initialize-AzRecoveryServicesDSMove cmdlet. Cmdlet ini sangat berguna untuk skenario pemindahan DS lintas penyewa.

## EXAMPLES

### Contoh 1: Memulai Pemindahan DS untuk salinan langganan silang
```powershell
PS C:\> Set-AzContext -SubscriptionName $targetSubscription
PS C:\> $validated = Test-AzRecoveryServicesDSMove -SourceVault $srcVault -TargetVault $trgVault -Force
PS C:\> Set-AzContext -SubscriptionName $sourceSubscription
PS C:\> if($validated) {
>>  $corr = Initialize-AzRecoveryServicesDSMove  -SourceVault $srcVault -TargetVault $trgVault
>> }
```

Cmdlet pertama mengatur konteks langganan target. Cmdlet kedua memicu beberapa validasi wajib pada penyimpanan target.
Cmdlet ketiga mengatur konteks langganan sumber.
Lalu berdasarkan Test-AzRecoveryServicesDSMove cmdlet, kami mengambil CorrelationId menggunakan Initialize-AzRecoveryServicesDSMove cmdlet. $corr dapat diinput ke cmdlet Salin.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.RecoveryServices.VAULT

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
