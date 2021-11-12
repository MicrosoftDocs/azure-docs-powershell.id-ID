---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
online version: https://docs.microsoft.com/en-us/powershell/module/az.recoveryservices/copy-azrecoveryservicesvault
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/RecoveryServices/RecoveryServices/help/Copy-AzRecoveryServicesVault.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/RecoveryServices/RecoveryServices/help/Copy-AzRecoveryServicesVault.md
ms.openlocfilehash: 630dc1a3a14beec147dec3f7bd2601ed0666ad78
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132408776"
---
# Copy-AzRecoveryServicesVault

## SYNOPSIS
Menyalin data dari vault di satu wilayah ke vault di kawasan lain.

## SINTAKS

```
Copy-AzRecoveryServicesVault [-Force] [-DefaultProfile <IAzureContextContainer>] [-SourceVault] <ARSVault>
 [-TargetVault] <ARSVault> [-RetryOnlyFailed] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Copy-AzRecoveryServicesVault** menyalin data dari vault di satu kawasan ke vault di kawasan lain. Saat ini kami hanya mendukung pemindahan data tingkat vault.

## CONTOH

### Contoh 1: Menyalin data dari vault1 ke vault2
```powershell
PS C:\> $sourceVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName1" -Name "vault1"
PS C:\> $targetVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName2" -Name "vault2"
PS C:\> Copy-AzRecoveryServicesVault -SourceVault $sourceVault -TargetVault $targetVault
```git 

The first two cmdlets fetch Recovery Services Vault - vault1 and vault2 respectively.
The second command triggers a complete data move from vault1 to vault2. 

### Example 2: Copy data from vault1 to vault2 with only failed items
```powershell
PS C:\> $sourceVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName1" -Name "vault1"
PS C:\> $targetVault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName2" -Name "vault2"
PS C:\> Copy-AzRecoveryServicesVault -SourceVault $sourceVault -TargetVault $targetVault -RetryOnlyFailed
```git 

The first two cmdlets fetch Recovery Services Vault - vault1 and vault2 respectively.
The second command triggers a partial data move from vault1 to vault2 with only those items which failed in previous move operations.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memaksa operasi pemindahan data (mencegah dialog konfirmasi) tanpa meminta konfirmasi untuk tipe kelebihan penyimpanan penyimpanan target. Parameter ini bersifat opsional. 

```yaml
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
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
Type: ARSVault
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
Type: ARSVault
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### Microsoft.Azure.Commands.RecoveryServices.VAULT

## OUTPUT

### System.String

## CATATAN

## LINK TERKAIT
