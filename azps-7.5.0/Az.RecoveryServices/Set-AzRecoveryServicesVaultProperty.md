---
external help file: Microsoft.Azure.PowerShell.Cmdlets.RecoveryServices.Backup.dll-Help.xml
Module Name: Az.RecoveryServices
ms.assetid: C2A7F37B-5713-4430-B83F-C6745692396D
online version: https://docs.microsoft.com/powershell/module/az.recoveryservices/set-azrecoveryservicesvaultproperty
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesVaultProperty.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/RecoveryServices/RecoveryServices/help/Set-AzRecoveryServicesVaultProperty.md
ms.openlocfilehash: 0cac9bb3405cd6c7fc3dfb4f2dc225f7c54a061d
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145647976"
---
# Set-AzRecoveryServicesVaultProperty

## SYNOPSIS
Memperbarui properti Vault.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.recoveryservices/set-azrecoveryservicesvaultproperty) untuk informasi terbaru.

## SYNTAX

### AzureRSVaultSoftDelteParameterSet (Default)
```
Set-AzRecoveryServicesVaultProperty [-SoftDeleteFeatureState <String>]
 [-DisableHybridBackupSecurityFeature <Boolean>] [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AzureRSVaultCMKParameterSet
```
Set-AzRecoveryServicesVaultProperty [-VaultId <String>] [-DefaultProfile <IAzureContextContainer>]
 -EncryptionKeyId <String> [-KeyVaultSubscriptionId <String>] [-InfrastructureEncryption]
 [-UseSystemAssignedIdentity <Boolean>] [-UserAssignedIdentity <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzRecoveryServicesVaultProperty** memperbarui properti vault layanan Pemulihan. Cmdlet ini dapat digunakan untuk mengaktifkan/menonaktifkan penghapusan sementara atau mengatur enkripsi CMK untuk vault dengan dua set parameter yang berbeda. 
**Properti SoftDeleteFeatureState** dari vault hanya dapat dinonaktifkan jika tidak ada kontainer terdaftar di vault. InfrastructurEncryption hanya dapat diatur saat pertama kali pengguna memperbarui vault CMK.

## EXAMPLES

### Contoh 1: Memperbarui SoftDeleteFeatureState dari vault
```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName"
$props = Set-AzRecoveryServicesVaultProperty -VaultId $vault.Id -SoftDeleteFeatureState Enable
```

Perintah pertama mendapatkan objek Vault dan kemudian menyimpannya dalam variabel $vault.
Perintah kedua Memperbarui properti SoftDeleteFeatureState dari vault ke status "Diaktifkan".

### Contoh 2: Memperbarui enkripsi CMK dari vault untuk menggunakan SystemAssigned MSIdentity

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName"
$keyVault = Get-AzKeyVault -VaultName "keyVaultName" -ResourceGroupName "RGName" 
$key = Get-AzKeyVaultKey -VaultName "keyVaultName" -Name "keyName" 
Set-AzRecoveryServicesVaultProperty -EncryptionKeyId $key.ID -InfrastructureEncryption -VaultId $vault.ID -UseSystemAssignedIdentity $true
```

Cmdlet pertama membuat RSVault memperbarui properti enkripsi. Cmdlet kedua mendapatkan brankas kunci azure. Cmdlet ketiga mendapatkan kunci dari brankas kunci.
Cmdlet keempat memperbarui kunci enkripsi yang dikelola pelanggan dalam RSVault untuk diakses melalui identitas SystemAssigned. Gunakan param -InfrastructureEncryption untuk mengaktifkan enkripsi infrastruktur untuk pembaruan pertama kali. 

### Contoh 3: Memperbarui enkripsi CMK vault untuk menggunakan userAssigned MSIdentity

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName"
$keyVault = Get-AzKeyVault -VaultName "keyVaultName" -ResourceGroupName "RGName" 
$key = Get-AzKeyVaultKey -VaultName "keyVaultName" -Name "keyName" 
Set-AzRecoveryServicesVaultProperty -EncryptionKeyId $key.ID -VaultId $vault.ID -UseSystemAssignedIdentity $false -UserAssignedIdentity $vault.Identity.UserAssignedIdentities.Keys[0]
```

Cmdlet pertama membuat RSVault memperbarui properti enkripsi. Cmdlet kedua mendapatkan brankas kunci azure. Cmdlet ketiga mendapatkan kunci dari brankas kunci.
Cmdlet keempat memperbarui kunci enkripsi yang dikelola pelanggan dalam RSVault untuk diakses melalui identitas UserAssigned.

### Contoh 4: Memperbarui HybridBackupSecurityFeature dari vault

```powershell
$vault = Get-AzRecoveryServicesVault -ResourceGroupName "rgName" -Name "vaultName"
$prop = Set-AzRecoveryServicesVaultProperty -VaultId $vault.Id -DisableHybridBackupSecurityFeature $false
```

Perintah pertama mendapatkan objek Vault dan kemudian menyimpannya dalam variabel $vault.
Perintah kedua menonaktifkan HybridBackupSecurityFeature dari vault, atur $true untuk mengaktifkannya lagi.

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

### -DisableHybridBackupSecurityFeature
Bendera opsional ($true/$false) untuk menonaktifkan/mengaktifkan pengaturan keamanan untuk pencadangan hibrid terhadap penghapusan yang tidak disengaja dan menambahkan lapisan autentikasi tambahan untuk operasi penting. Berikan $false untuk mengaktifkan keamanan.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: AzureRSVaultSoftDelteParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionKeyId
KeyId kunci enkripsi yang akan digunakan untuk CMK.

```yaml
Type: System.String
Parameter Sets: AzureRSVaultCMKParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InfrastructureEncryption
Mengaktifkan enkripsi infrastruktur pada vault ini. Enkripsi infrastruktur harus diaktifkan saat mengonfigurasi enkripsi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AzureRSVaultCMKParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultSubscriptionId
Id Langganan Key Vault.

```yaml
Type: System.String
Parameter Sets: AzureRSVaultCMKParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SoftDeleteFeatureState
SoftDeleteFeatureState dari Vault Layanan Pemulihan.

```yaml
Type: System.String
Parameter Sets: AzureRSVaultSoftDelteParameterSet
Aliases:
Accepted values: Enable, Disable

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserAssignedIdentity
ID ARM dari UserAssigned Identity yang akan digunakan untuk enkripsi CMK. Berikan parameter ini jika UseSystemAssignedIdentity $false.

```yaml
Type: System.String
Parameter Sets: AzureRSVaultCMKParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSystemAssignedIdentity
Bendera Boolean untuk menunjukkan apakah SystemAssigned Identity akan digunakan untuk enkripsi CMK. Vaules yang Diterima: $true, $false

```yaml
Type: System.Boolean
Parameter Sets: AzureRSVaultCMKParameterSet
Aliases:

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

### System.String

### Microsoft.Azure.Commands.RecoveryServices.Backup.Cmdlets.Models.VaultSoftDeleteFeatureState

## OUTPUTS

### Microsoft.Azure.Management.RecoveryServices.Backup.Models.BackupResourceVaultConfigResource

## NOTES

## RELATED LINKS

[Get-AzRecoveryServicesVault](./Get-AzRecoveryServicesVault.md)

[Get-AzRecoveryServicesVaultProperty](./Get-AzRecoveryServicesVaultProperty.md)
