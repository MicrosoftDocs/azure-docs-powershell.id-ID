---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/copy-azrecoveryservicesvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Copy-AzRecoveryServicesVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Copy-AzRecoveryServicesVault.md
ms.openlocfilehash: 694ab8b21aba180560a21318efb566cbc1559c2d
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136732288"
---
# Copy-AzRecoveryServicesVault

## SYNOPSIS
Menyalin data dari vault di satu wilayah ke vault di kawasan lain.

## SYNTAX

### AzureRSVaultDataMoveParameterSet (Default)
```
Copy-AzRecoveryServicesVault [-Force] [-DefaultProfile <IAzureContextContainer>] [-SourceVault] <ARSVault>
 [-TargetVault] <ARSVault> [-RetryOnlyFailed] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AzureRSVaultTriggerMoveParameterSet
```
Copy-AzRecoveryServicesVault [-Force] -CorrelationIdForDataMove <String>
 [-DefaultProfile <IAzureContextContainer>] [-SourceVault] <ARSVault> [-TargetVault] <ARSVault> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Copy-AzRecoveryServicesVault** menyalin data dari vault di satu kawasan ke vault di kawasan lain. Saat ini kami hanya mendukung pemindahan data tingkat vault.

## EXAMPLES

### Contoh 1: Menyalin data dari vault1 ke vault2

```powershell
PS C:\> $sourceVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName1" -Name "vault1"
PS C:\> $targetVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName2" -Name "vault2"
PS C:\> Copy-AzRecoveryServicesVault -SourceVault $sourceVault -TargetVault $targetVault
```

Dua cmdlet pertama masing-masing mengambil Vault Layanan Pemulihan - vault1 dan vault2. Perintah kedua memicu pemindahan data lengkap dari vault1 ke vault2. $sourceVault dan $targetVault juga termasuk dalam langganan yang sama tanent, dapat diambil dengan mengatur konteks langganan yang berbeda.

### Contoh 2: Menyalin data dari vault1 ke vault2 dengan item yang gagal saja

```powershell
PS C:\> $sourceVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName1" -Name "vault1"
PS C:\> $targetVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName2" -Name "vault2"
PS C:\> Copy-AzRecoveryServicesVault -SourceVault $sourceVault -TargetVault $targetVault -RetryOnlyFailed
```

Dua cmdlet pertama masing-masing mengambil Vault Layanan Pemulihan - vault1 dan vault2.
Perintah kedua memicu pemindahan data parsial dari vault1 ke vault2 hanya dengan item yang gagal dalam operasi pemindahan sebelumnya.
$sourceVault dan $targetVault juga termasuk dalam langganan yang sama tanent, dapat diambil dengan mengatur konteks langganan yang berbeda.

## PARAMETERS

### -CorrelationIdForDataMove
Id Korelasi untuk memicu Pemindahan DS.

```yaml
Type: System.String
Parameter Sets: AzureRSVaultTriggerMoveParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Memaksa operasi pemindahan data (mencegah dialog konfirmasi) tanpa meminta konfirmasi untuk tipe kelebihan penyimpanan vault target. Parameter ini bersifat opsional. 

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

### -RetryOnlyFailed
Alihkan parameter untuk mencoba pemindahan data hanya untuk wadah dalam vault sumber yang belum dipindahkan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureRSVaultDataMoveParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceVault
Objek vault sumber yang akan dipindahkan.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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

### System.String

## CATATAN

## RELATED LINKS
