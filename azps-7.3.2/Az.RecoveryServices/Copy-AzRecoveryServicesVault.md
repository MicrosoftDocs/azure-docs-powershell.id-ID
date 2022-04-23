---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/copy-azrecoveryservicesvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Copy-AzRecoveryServicesVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Copy-AzRecoveryServicesVault.md
ms.openlocfilehash: 310096f4f54a293382869d3f2efeade8326edbdc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143072801"
---
# Copy-AzRecoveryServicesVault

## SYNOPSIS
Menyalin data dari kubah di satu kawasan ke kubah di kawasan lain.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/copy-azrecoveryservicesvault) untuk informasi terbaru.

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
Cmdlet **Copy-AzRecoveryServicesVault** menyalin data dari kubah di satu kawasan ke kubah di wilayah lain. Saat ini kami hanya mendukung perpindahan data tingkat kubah.

## EXAMPLES

### Contoh 1: Salin data dari vault1 ke vault2

```powershell
PS C:\> $sourceVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName1" -Name "vault1"
PS C:\> $targetVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName2" -Name "vault2"
PS C:\> Copy-AzRecoveryServicesVault -SourceVault $sourceVault -TargetVault $targetVault
```

Dua cmdlet pertama mengambil Vault Layanan Pemulihan - vault1 dan vault2. Perintah kedua memicu perpindahan data lengkap dari vault1 ke vault2. $sourceVault dan $targetVault juga dapat tergabung dalam langganan yang berbeda dalam satu kesatuan yang sama, dapat dilakukan dengan mengatur konteks langganan yang berbeda.

### Contoh 2: Salin data dari vault1 ke vault2 hanya dengan item yang gagal

```powershell
PS C:\> $sourceVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName1" -Name "vault1"
PS C:\> $targetVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName2" -Name "vault2"
PS C:\> Copy-AzRecoveryServicesVault -SourceVault $sourceVault -TargetVault $targetVault -RetryOnlyFailed
```

Dua cmdlet pertama mengambil Vault Layanan Pemulihan - vault1 dan vault2.
Perintah kedua memicu perpindahan sebagian data dari vault1 ke vault2 hanya dengan item yang gagal dalam operasi perpindahan sebelumnya.
$sourceVault dan $targetVault juga dapat tergabung dalam langganan yang berbeda dalam satu kesatuan yang sama, dapat dilakukan dengan mengatur konteks langganan yang berbeda.

## PARAMETERS

### -CorrelationIdForDataMove
Id Korlasi untuk memicu Pemindahan DS.

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

### -Paksa
Memaksa operasi pemindahan data (mencegah dialog konfirmasi) tanpa meminta konfirmasi untuk tipe redundansi penyimpanan kubah target. Parameter ini bersifat opsional. 

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
Alihkan parameter untuk mencoba pemindahan data hanya untuk kontainer dalam kubah sumber yang belum dipindahkan.

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
Objek kubah sumber yang akan dipindahkan.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

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

## NOTES

## RELATED LINKS
