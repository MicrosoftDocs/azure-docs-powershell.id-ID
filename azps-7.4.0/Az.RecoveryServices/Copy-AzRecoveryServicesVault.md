---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/copy-azrecoveryservicesvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Copy-AzRecoveryServicesVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Copy-AzRecoveryServicesVault.md
ms.openlocfilehash: a7da59c96cb740fbaf93ae4a49d5a40a95738a78
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144725328"
---
# Copy-AzRecoveryServicesVault

## SYNOPSIS
Menyalin data dari vault di satu wilayah ke vault di wilayah lain.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/copy-azrecoveryservicesvault) untuk informasi terbaru.

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
Cmdlet **Copy-AzRecoveryServicesVault** menyalin data dari vault di satu wilayah ke vault di wilayah lain. Saat ini kami hanya mendukung pemindahan data tingkat vault.

## EXAMPLES

### Contoh 1: Menyalin data dari vault1 ke vault2

```powershell
$sourceVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName1" -Name "vault1"
$targetVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName2" -Name "vault2"
Copy-AzRecoveryServicesVault -SourceVault $sourceVault -TargetVault $targetVault
```

Dua cmdlet pertama mengambil Vault Layanan Pemulihan - vault1 dan vault2 masing-masing. Perintah kedua memicu pemindahan data lengkap dari vault1 ke vault2. $sourceVault dan $targetVault juga dapat menjadi milik langganan yang berbeda dalam tanent yang sama, dapat diambil dengan mengatur konteks langganan yang berbeda.

### Contoh 2: Menyalin data dari vault1 ke vault2 hanya dengan item yang gagal

```powershell
$sourceVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName1" -Name "vault1"
$targetVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName2" -Name "vault2"
Copy-AzRecoveryServicesVault -SourceVault $sourceVault -TargetVault $targetVault -RetryOnlyFailed
```

Dua cmdlet pertama mengambil Vault Layanan Pemulihan - vault1 dan vault2 masing-masing.
Perintah kedua memicu pemindahan data parsial dari vault1 ke vault2 hanya dengan item yang gagal dalam operasi pemindahan sebelumnya.
$sourceVault dan $targetVault juga dapat menjadi milik langganan yang berbeda dalam tanent yang sama, dapat diambil dengan mengatur konteks langganan yang berbeda.

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
Memaksa operasi pemindahan data (mencegah dialog konfirmasi) tanpa meminta konfirmasi untuk jenis redundansi penyimpanan vault target. Parameter ini bersifat opsional. 

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
Alihkan parameter untuk mencoba pemindahan data hanya untuk kontainer di vault sumber yang belum dipindahkan.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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
